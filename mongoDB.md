# MongoDB 3.2 to 7 
```
/data/db
|-- ProjectA
|   |-- collection-0-ProjectA-user.wt
|   |-- collection-1-ProjectA-log.wt
|   |-- collection-2-ProjectA-transaction.wt
|   |-- index-0-ProjectA-user.wt
|   |-- index-1-ProjectA-log.wt
|   |-- index-2-ProjectA-transaction.wt
|   |-- WiredTigerLog.0000000001
|   |-- WiredTigerLog.0000000002
|-- WiredTiger
|-- WiredTiger.lock
|-- WiredTiger.turtle
|-- WiredTiger.wt
|-- WiredTiger.wtcheckpoint
```
- ProjectA is the DB which can have multiple Table/collection - like has 3 different table user, log and transaction
- index will tell where data is present
- data will be stored into user collection-0-ProjectA-user.wt
- if data Grows - Sharding Setup: You configure MongoDB to use sharding and specify a shard key.

```
/data/db/shard1
|-- ProjectA
|   |-- collection-0-ProjectA-user.wt
|   |-- collection-1-ProjectA-log.wt
|   |-- collection-2-ProjectA-transaction.wt
/data/db/shard2
|-- ProjectA
|   |-- collection-0-ProjectA-user.wt
|   |-- collection-1-ProjectA-log.wt
|   |-- collection-2-ProjectA-transaction.wt
```
## Q.2 ORM Mongoose why it required 

- Without Mongoose, you'd have to handle a lot of low-level details manually
```
const { MongoClient } = require('mongodb');

async function run() {
  const client = new MongoClient('mongodb://localhost:27017', { useNewUrlParser: true, useUnifiedTopology: true });

  try {
    await client.connect();
    console.log('Connected to MongoDB');

    const db = client.db('ProjectA');
    const users = db.collection('users');

    // Insert a document
    const newUser = { name: 'Alice', email: 'alice@example.com', age: 30 };
    await users.insertOne(newUser);
    console.log('User inserted:', newUser);

    // Find documents
    const foundUsers = await users.find({ age: { $gte: 18 } }).toArray();
    console.log('Adult users:', foundUsers);

    // Update a document
    await users.updateOne({ name: 'Alice' }, { $set: { age: 31 } });
    console.log('User updated');

    // Delete a document
    await users.deleteOne({ name: 'Alice' });
    console.log('User deleted');
  } finally {
    await client.close();
  }
}

run().catch(console.error);
```

### with Mongoose 
```
const mongoose = require('mongoose');

mongoose.connect('mongodb://localhost:27017/ProjectA', { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log('Connected to MongoDB'))
  .catch(err => console.error('Connection error:', err));

// Define a schema
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true,
    unique: true
  },
  age: {
    type: Number,
    required: true
  }
});

// Create a model
const User = mongoose.model('User', userSchema);

// Create and save a document
const createUser = async () => {
  const newUser = new User({ name: 'Alice', email: 'alice@example.com', age: 30 });
  await newUser.save();
  console.log('User saved:', newUser);
};

// Find documents
const findUsers = async () => {
  const users = await User.find({ age: { $gte: 18 } });
  console.log('Adult users:', users);
};

// Update a document
const updateUser = async () => {
  await User.updateOne({ name: 'Alice' }, { $set: { age: 31 } });
  console.log('User updated');
};

// Delete a document
const deleteUser = async () => {
  await User.deleteOne({ name: 'Alice' });
  console.log('User deleted');
};

// Run the operations
(async () => {
  await createUser();
  await findUsers();
  await updateUser();
  await deleteUser();
})().catch(console.error);
```
## Q. Mongoose Annotations

- Defining a Schema with Annotations:

const mongoose = require('mongoose');
```
// Define a schema for a 'User' collection
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true, // Annotation: This field is required
  },
  email: {
    type: String,
    required: true,
    unique: true, // Annotation: This field must be unique
  },
});

// Create a model from the schema
const User = mongoose.model('User', userSchema);
```

- Schema Annotations with Validation:

```
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: [true, 'Name is required'], // Annotation: Custom error message for required validation
    minlength: [3, 'Name must be at least 3 characters long'] // Annotation: Minimum length validation
  },
  email: {
    type: String,
    required: [true, 'Email is required'],
    unique: true,
    match: [/^\S+@\S+\.\S+$/, 'Email is not valid'] // Annotation: Regular expression validation
  },
});
```

- Using Pre and Post Hooks (Middleware):

```
// Pre-save hook to perform actions before saving a document
userSchema.pre('save', function(next) {
  this.updated_at = new Date();
  next();
});
```
```
// Post-save hook to perform actions after saving a document
userSchema.post('save', function(doc, next) {
  console.log('User has been saved:', doc);
  next();
});
```
- Virtuals and Methods:
```
// Define a virtual property
userSchema.virtual('fullName').get(function() {
  return `${this.firstName} ${this.lastName}`;
});

// Define instance methods
userSchema.methods.greet = function() {
  return `Hello, my name is ${this.name}`;
};

// Define static methods
userSchema.statics.findByEmail = function(email) {
  return this.findOne({ email });
};

// Example usage
const User = mongoose.model('User', userSchema);

const user = new User({ name: 'Alice', email: 'alice@example.com', age: 30 });
console.log(user.greet()); // "Hello, my name is Alice"
```

## Q. sample varios validation Annotation 
- Type Annotations:Specifies `data types`
  ```
  name: { type: String}
  ```
- Required: Ensures the field has a value.
  ```
    name: { type: String, required: true }
  ```

- Unique: Ensures the field value is unique.
  ```
  email: { type: String, unique: true }
  ```

- Default: Specifies a default value for the field.
  ```
    createdAt: { type: Date, default: Date.now }
  ```
- Min/Max: Validates numerical and date values.
```
  age: { type: Number, min: 0, max: 120 }
```
- Minlength/Maxlength: Validates string length.
```
  name: { type: String, minlength: 3, maxlength: 50 }
```
- Match: Validates the field value against a regex.
  ```
    email: { type: String, match: /^\S+@\S+\.\S+$/ }
  ```
- Enum: Validates the field value within a set of values.
  ```
    status: { type: String, enum: ['active', 'inactive', 'suspended'] }
  ```

- Custom: Allows custom validation logic.
  ```

  const userSchema = new mongoose.Schema({
  age: {
    type: Number,
    validate: {
      validator: function(v) {
        return v >= 0 && v <= 120;
      },
      message: props => `${props.value} is not a valid age!`
    }}})
```

- Indexing: Creates an index for faster querying.

```
  email: { type: String, index: true }
```
- example

```
const userSchema = new mongoose.Schema({
  name: {
    type: String,
    required: [true, 'Name is required'],
    minlength: [3, 'Name must be at least 3 characters long'],
    maxlength: [50, 'Name must be less than 50 characters long']
  },
  email: {
    type: String,
    required: [true, 'Email is required'],
    unique: true,
    match: [/^\S+@\S+\.\S+$/, 'Email is not valid']
  },
  age: {
    type: Number,
    required: true,
    min: [0, 'Age must be a positive number'],
    max: [120, 'Age must be less than 120'],
    validate: {
      validator: function(v) {
        return v >= 0 && v <= 120;
      },
      message: props => `${props.value} is not a valid age!`
    }
  },
  status: {
    type: String,
    enum: ['active', 'inactive', 'suspended'],
    default: 'active'
  },
  createdAt: {
    type: Date,
    default: Date.now
  }
})
```

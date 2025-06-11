
// ############################################
// login via Remote using putty
// ssh roo@ipAddress
// ##############################

// 1)create Images from fresh code 
// docker build -t <projectName> .
// eg 
// docker build -t ravi-ui .

// 2) login to Docker in Redhat & provide the password from SSH token redhat 
// docker login -u kubeadmin default-route-openshift-image-registry.apps-crc.testing
// eg. 
// docker login -u kubeadmin default default-route-openshift-image-registry.apps.ravi.tre.nsn-rdnet.net
// provide the password from SSH token redhat 
// 2) tag 
// docker tag <imageName> default-route-openshift-image-registry.apps-crc.testing/<namespace>/imageName
// eg. 
// docker tag ravi-ui default-route-openshift-image-registry.apps.ravi.tre.nsn-rdnet.net/ravicoe/ravi-ui

// 3) push 
// docker push default-route-openshift-image-registry.apps-crc.testing/<namespace>/imageName
// docker push default-route-openshift-image-registry.apps.ravi.tre.nsn-rdnet.net/ravicoe/ravi-ui
// 4) update yaml file path of image to pick: Set Up Kubernetes Deployment
// Deployment-ui_dev.yaml

// 5) apply the deployment 
// oc apply -f Deployment-ui_dev.yaml

// oc project ravicoe
// oc apply -f Deployment-ui_dev.yaml
// oc get pods 

// ############################################
// Complete Pipeline CI/CD pipeline 
// define script and jobs in gitlab-ci.yml
// ############################################
// .gitlab-ci.yml File:
// ############################################
// stages:
//   - build
//   - test
//   - deploy

// build-job:
//   stage: build
//   script:
//     - docker build -t $CI_REGISTRY/my-app .  //build image 

// test-job:
//   stage: test
//   script:
//     - docker run $CI_REGISTRY/my-app ./run-tests.sh

// deploy-job:
//   stage: deploy
//   script:
//     - echo "Deploying the application..."
//     - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
//     - docker push $CI_REGISTRY/my-app
//     - kubectl apply -f deployment.yaml
	
// ################
// Image Tagging: The image should have been tagged during the build stage 
// 	(e.g., docker build -t $CI_REGISTRY/my-app .). This command pushes that tagged image to the registry.

// Sure, let's break down the `deploy-job` step by step:

// ###  Deploy Job Breakdown 

// ####  1. Stage: Deploy 
// This specifies that the job is part of the `deploy` stage in your CI/CD pipeline.

// ####  2. Script Section 
// The `script` section contains the commands that will be executed during this job.

// #####  Step-by-Step Explanation: 

// 1.  Echo Command :
//   - echo "Deploying the application..."
   
//   - This simply prints "Deploying the application..." to the console for logging purposes.

// 2.  Docker Login :
//   - docker login -u $CI_REGISTRY_USER -p $CI_REGISTRY_PASSWORD $CI_REGISTRY
   
//   -  Purpose : Logs into the Docker registry using the provided credentials.
//   -  Environment Variables : 
//     - `$CI_REGISTRY_USER`: The username for the Docker registry.
//     - `$CI_REGISTRY_PASSWORD`: The password for the Docker registry.
//     - `$CI_REGISTRY`: The URL of the Docker registry.

// 3.  Docker Push :
//   - docker push $CI_REGISTRY/my-app
   
//   -  Purpose : Pushes the Docker image to the specified Docker registry.
//   -  Image Tagging : The image should have been tagged during the build stage (e.g., `docker build -t $CI_REGISTRY/my-app .`). This command pushes that tagged image to the registry.

// 4.  Kubernetes Deployment :
  
// 	- kubectl apply -f deployment.yaml

//   -  Purpose : Applies the Kubernetes deployment configuration defined in `deployment.yaml`.
//   -  Deployment : This command updates the Kubernetes cluster with the new image, effectively deploying the application.

// ###  How It Works Together 

// 1.  Image Creation :
//   - The image is created during the `build` stage with a command like `docker build -t $CI_REGISTRY/my-app .`.

// 2.  Image Tagging :
//   - The `-t` option in the `docker build` command tags the image with the specified name and registry path (e.g., `$CI_REGISTRY/my-app`).

// 3.  Image Pushing :
//   - The `docker push` command pushes the tagged image to the Docker registry.

// 4.  Final Deployment :
//   - The `kubectl apply -f deployment.yaml` command updates the Kubernetes cluster with the new image, completing the deployment process.

// The deployment.yaml file defines how your application should be deployed in the Kubernetes cluster

// ###  Example of a Complete Pipeline 

// Here's how the complete `.gitlab-ci.yml` might look with the build, test, and deploy stages:

// ########################################

// Q. A Dockerfile is a text file that contains a series of instructions on how to build a Docker image. It automates the process of creating a Docker image by specifying the environment and the steps needed to set up the application.
// docker file example 
// FROM node:14
// WORKDIR /app
// COPY . .
// RUN npm install
// CMD ["npm", "start"]

// Dockerfile: A script with instructions to build a Docker image.
// Docker Image: A packaged environment with everything needed to run an application.
// Container: A running instance of a Docker image.

// Run the Container:

// Once the image is built, you can run it as a container using the command docker run -p 3000:3000 my-app. 
// This starts a new container from the my-app image and maps port 3000 of the container to port 3000 on your host machine.
// -----------

// apiVersion: apps/v1
// kind: Deployment
// metadata:
//   name: my-app
// spec:
//   replicas: 2
//   selector:
//     matchLabels:
//       app: my-app
//   template:
//     metadata:
//       labels:
//         app: my-app
//     spec:
//       containers:
//       - name: my-app
//         image: my-app:latest    //provide the image path here to pick 
//         ports:					// ports: Ports to expose from the container.
//         - containerPort: 3000   //containerPort: The port the container listens on (3000).
// ---
// apiVersion: v1
// kind: Service
// metadata:
//   name: my-app-service
// spec:
//   selector:
//     app: my-app
//   ports:
//     - protocol: TCP
//       port: 80   //Explanation: This means that the Service will listen on port 80. When external traffic reaches the Service, it will come in through this port.
//       targetPort: 3000  //Explanation: This means that the Service will forward the incoming traffic from port 80 to port 3000 on the Pods.
//   type: LoadBalancer

// ================

// Deployment: Manages the creation and scaling of Pods.
// Creating Pods:
// 	The Deployment creates Pods, which are instances of your application running in containers.
// 	Each Pod uses the Docker image my-app:latest.
// Service: Exposes the Pods to the outside world and balances the load.
// 		The Service exposes your application to the outside world.
// 		In this example, it maps port 80 of the Service to port 3000 of the Pods, 
// 		making the application accessible via the Service's external IP.
const str ='hi this is me '
console.log(str.startsWith('hi'))


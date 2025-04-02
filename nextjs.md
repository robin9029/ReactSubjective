- ✅ Blazing Fast Performance – Thanks to Server-side Rendering (SSR) and Static Site Generation (SSG), pages load almost instantly. 
- ✅ Built-in API Routes – No need for a separate backend; Next.js lets you create API endpoints effortlessly.
- ✅ Image Optimization – The next/image component ensures images load efficiently without extra effort.
- ✅ SEO Supercharged – With SSR & SSG, pages are optimized for search engines out of the box.
- ✅ Full-stack Capabilities – Seamlessly integrate front-end and backend logic in a single project.

## SEO 
### static
  - inside header mentions- **Metadata** 
  - title
  - description
  - keywords[]
  - opengraph: [ title, description, images=[] ]  // Images

 ![Screenshot 2025-04-02 at 11 49 42 AM](https://github.com/user-attachments/assets/f4f2f393-64b5-480e-a1b9-4a1e41644c3b)

- you tells Google crawler what type of website it is and you can provide the Twitter, Linkdelin etc
  
### Dynamic
  - roboy.txt Object: allows what all sites you are allowing for SEO
  - you give the rules what are website you want to allow, disallow , sitemap of product etc 
      ```
      User-Agent: *
      Allow: /
      Disallow: /private/

      Sitemap: https://acme.com/sitemap.xml

   - sitemap.xml
![Screenshot 2025-04-02 at 11 50 32 AM](https://github.com/user-attachments/assets/37c3b299-64e4-4952-b55d-31416ee4e042)

- sitemap: a special file that matches the Sitemaps XML format to help search engine crawlers index your site more efficiently

- first Fetch the number of product & the number of sitemaps needed
```
  export async function generateSitemaps() {
  // Fetch the total number of products and calculate the number of sitemaps needed
  return [{ id: 0 }, { id: 1 }, { id: 2 }, { id: 3 }]
}
```
- Provides the sitemap which tells URL,LASTModified, Changed frequntly ?
```
export default function sitemap(): MetadataRoute.Sitemap {
  return [
    {
      url: 'https://acme.com',
      lastModified: new Date(),
      changeFrequency: 'yearly',
      priority: 1,
    }
  ```
- It generate the Sitemap.XML which helps for Crawleing.
  -  https://nextjs.org/docs/app/api-reference/file-conventions/metadata/sitemap


## Next js VS react JS
- Nextjs during build time fetch the data and create HTML and css : data is prefetched - pre load data 
- React js - create JS Object 
- Js object is heavy as compared to HTML CSS
- React - SEO Performance is very bad - load- Application-Data fecth- data comes - display data : set scores down 
- Client side rendering and server side rendering  & Static Randering 
- React uses - web pack for bundler 
- Next uses RUST internally which makes fast - is versel 

## Routing in Next JS
- Pages / inside 
- Index which maps to /
- About.js inside Pages so React creates its routing 
- Nested routing - user/myname/
- useRouter 
- solves Router React router dom 

## Redering 
- Client side renedering : Normal as REACT JS
- server side rendering : getServerSideProps 
```
export const getServerSideProps = async () =>{
    const Finaldata = fetch(URL).then(data=>data.json())
    Return  {props:{data: Finaldata}}
      }
```
- Static Randering : getStaticProps


  

    

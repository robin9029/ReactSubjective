- ✅ Blazing Fast Performance – Thanks to Server-side Rendering (SSR) and Static Site Generation (SSG), pages load almost instantly. 
- ✅ Built-in API Routes – No need for a separate backend; Next.js lets you create API endpoints effortlessly.
- ✅ Image Optimization – The next/image component ensures images load efficiently without extra effort.
- ✅ SEO Supercharged – With SSR & SSG, pages are optimized for search engines out of the box.
- ✅ Full-stack Capabilities – Seamlessly integrate front-end and backend logic in a single project.

## SEO 
- static

  inside header mentions- Metadata 
  - title
  - description
  - keywords[]
  - opengraph: [ title, description, images=[] ]  // Images
- Dynamic
    - roboy.txt Object: allows what all sites you are allowing for SEO
      ```
      User-Agent: *
      Allow: /
      Disallow: /private/

      Sitemap: https://acme.com/sitemap.xml

   - sitemap.xml
     
```
  export async function generateSitemaps() {
  // Fetch the total number of products and calculate the number of sitemaps needed
  return [{ id: 0 }, { id: 1 }, { id: 2 }, { id: 3 }]
}
```

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

  

    

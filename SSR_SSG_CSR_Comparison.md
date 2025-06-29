
# SSR vs SSG vs CSR

This guide explains the difference between **SSR (Server-Side Rendering)**, **SSG (Static Site Generation)**, and **CSR (Client-Side Rendering)**.

------------

## What They Are

### 1. **SSR – Server-Side Rendering**
- **Definition**: The HTML is generated on the **server** for each request.
- **How it works**: When a user visits a page, the server generates the HTML with actual data and sends it to the browser.
- **Example**: Laravel Blade templates, or using Nuxt.js with SSR.

#### Pros:
- Great for SEO
- Fast first page load
- Always up-to-date content

#### Cons:
- More load on the server
- Slower interactions after initial load

---

### 2. **SSG – Static Site Generation**
- **Definition**: The HTML is **pre-built at build time** (not on request).
- **How it works**: When you deploy your app, it generates HTML pages for each route. These are served as static files.
- **Example**: Nuxt `generate`, Next.js with `getStaticProps()`, or using Laravel with Laravel Static Site Generator.

####  Pros:
- Very fast performance (static files)
- Scalable (uses CDN)
- No server needed

####  Cons:
- Content is not real-time (requires rebuild)
- Not suitable for highly dynamic pages

---

### 3. **CSR – Client-Side Rendering**
- **Definition**: HTML is minimal; content is generated by JavaScript **in the browser**.
- **How it works**: Server sends a basic HTML and a JavaScript bundle. Then the browser renders the page using JS.
- **Example**: Pure Vue.js SPA or React SPA.

#### Pros:
- Fast after initial load
- Smooth user interaction (SPA behavior)

#### Cons:
- Poor SEO (unless you use pre-rendering)
- Slower first load (blank screen until JS loads)

---

| Feature              | SSR                       | SSG                        | CSR                         |
|----------------------|---------------------------|----------------------------|-----------------------------|
| Rendered where?     | Server at request time    | Server at build time       | Browser                     |
| Speed (First Load)  | Fast                      | Fastest                    | Slowest                     |
| SEO Friendly        | Yes                      |  Yes                      | ❌ Not by default           |
| Content Freshness   | Always up-to-date         | Needs rebuild              | Fetched on browser          |
| Example Tech        | Laravel + Blade, Nuxt SSR | Nuxt Generate, Hugo        | Vue SPA, React SPA          |

---

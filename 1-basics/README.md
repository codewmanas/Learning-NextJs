# Basics of Next.js

## What is Next.js?

Next.js is a powerful React framework that enables developers to build fast, scalable, and SEO-friendly web applications. It provides a hybrid approach to rendering, combining the best of server-side rendering (SSR), static site generation (SSG), and client-side rendering (CSR). Developed by Vercel, Next.js simplifies the development process by offering built-in features like routing, API handling, and performance optimization.

### Key Features of Next.js:
- **File-based Routing**: Simplifies routing by using the file system.
- **Server-side Rendering (SSR)**: Renders pages on the server for better SEO and faster initial load.
- **Static Site Generation (SSG)**: Pre-renders pages at build time for improved performance.
- **API Routes**: Allows you to create serverless API endpoints.
- **Automatic Code Splitting**: Loads only the necessary JavaScript for each page.
- **Built-in CSS and Sass Support**: Simplifies styling.
- **Image Optimization**: Automatically optimizes images for better performance.

---

## Why is Next.js Important?

Next.js is important because it addresses many challenges faced by modern web developers:
1. **SEO Optimization**: By supporting SSR and SSG, Next.js ensures that search engines can easily crawl and index your content.
2. **Performance**: Features like automatic code splitting and image optimization make applications faster.
3. **Developer Experience**: With built-in routing, API handling, and hot reloading, developers can focus on building features rather than configuring tools.
4. **Scalability**: Next.js supports both static and dynamic content, making it suitable for projects of any size.
5. **Flexibility**: You can choose the rendering method (SSR, SSG, or CSR) that best suits your application.

---

## Routing in Next.js

Routing in Next.js is file-based, meaning the structure of your `pages` directory determines the routes of your application. This eliminates the need for a separate routing configuration.

### Basics of Routing

1. **File-Based Routing**:
     - Each file in the `pages` directory corresponds to a route.
     - For example:
       ```
       pages/index.js       -> '/'
       pages/about.js       -> '/about'
       pages/contact.js     -> '/contact'
       ```

2. **Dynamic Routes**:
     - You can create dynamic routes by using square brackets in filenames.
     - For example:
       ```
       pages/post/[id].js   -> '/post/:id'
       ```
     - Access the dynamic parameter (`id`) using `useRouter` or `getStaticProps`/`getServerSideProps`.

3. **Nested Routes**:
     - Create subdirectories in the `pages` folder to define nested routes.
     - For example:
       ```
       pages/blog/index.js  -> '/blog'
       pages/blog/post.js   -> '/blog/post'
       ```

4. **API Routes**:
     - Next.js allows you to define API endpoints in the `pages/api` directory.
     - For example:
       ```
       pages/api/hello.js   -> '/api/hello'
       ```

5. **Custom 404 Page**:
     - Create a `404.js` file in the `pages` directory to define a custom 404 error page.

---

### Advanced Routing Concepts

1. **Catch-All Routes**:
     - Use `[...param].js` to match all routes under a specific path.
     - For example:
       ```
       pages/blog/[...slug].js -> '/blog/*'
       ```

2. **Optional Catch-All Routes**:
     - Use `[[...param]].js` to make the catch-all route optional.
     - For example:
       ```
       pages/blog/[[...slug]].js -> '/blog' or '/blog/*'
       ```

3. **Linking Between Pages**:
     - Use the `Link` component from `next/link` for client-side navigation.
     - Example:
       ```jsx
       import Link from 'next/link';

       export default function Home() {
           return (
               <div>
                 <Link href="/about">Go to About Page</Link>
               </div>
           );
       }
       ```

4. **Programmatic Navigation**:
     - Use the `useRouter` hook for programmatic navigation.
     - Example:
       ```jsx
       import { useRouter } from 'next/router';

       export default function Home() {
           const router = useRouter();

           const navigateToAbout = () => {
               router.push('/about');
           };

           return <button onClick={navigateToAbout}>Go to About Page</button>;
       }
       ```

---

## Summary

Next.js is a versatile framework that simplifies the development of modern web applications. Its file-based routing system is intuitive and powerful, allowing developers to create both static and dynamic routes effortlessly. By mastering routing in Next.js, you can build scalable, SEO-friendly, and high-performance applications.

Happy coding!
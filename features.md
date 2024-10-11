# **Folonite.js Features**

Here’s how you can structure the index or feature listing in your documentation with links to the respective sections for each feature. I’ve added anchor links to each feature so users can easily jump to the detailed explanation of each one.

---

## **Folonite.js Features**

Folonite.js offers a range of core and advanced features that enable developers to build dynamic, scalable web applications with ease. Below is a list of key features with links to their detailed descriptions:

1. [Dynamic Server-Side Rendering (SSR)](#dynamic-server-side-rendering-ssr)
2. [Streaming Content](#streaming-content)
3. [Hot Reloading (Development Mode)](#hot-reloading-development-mode)
4. [Component-Based Architecture](#component-based-architecture)
5. [Built-in External Component Marketplace](#built-in-external-component-marketplace)
6. [Advanced CLI (Command-Line Interface)](#advanced-cli-command-line-interface)
7. [Auto Dependency Management](#auto-dependency-management)
8. [API Handling with JSON Parsing and Authentication](#api-handling-with-json-parsing-and-authentication)

---

### **1. Dynamic Server-Side Rendering (SSR)**

**Server-Side Rendering (SSR)** in Folonite.js allows your pages to be rendered on the server before they are sent to the client. This improves performance, SEO, and initial load times by reducing the client-side rendering overhead. Folonite.js dynamically renders components based on incoming requests, allowing for real-time, data-driven applications.

### **How to Use SSR**:
- Folonite.js automatically supports SSR. To run the server with SSR enabled, use the following command:
```bash
npm start
```
- This starts the server and renders pages on the server before sending them to the client.

### **Key Use Cases**:
- **SEO-Driven Websites**: When SEO is a priority (such as for blogs or e-commerce stores), SSR ensures that search engines can crawl and index your content easily.
- **Performance Optimization**: SSR reduces the load on the client by sending pre-rendered HTML, leading to faster page loads, especially on slower devices or networks.

### **Benefits**:
- **Improved SEO**: Content is fully rendered before it reaches the client, making it easier for search engines to index.
- **Faster Load Times**: Initial page load is quicker since HTML is sent pre-rendered.
- **Better User Experience**: Pages load seamlessly, even on slower devices or networks.

---

### **2. Streaming Content**

Folonite.js allows for **content streaming**, where parts of a page are progressively sent to the client as they are ready, rather than waiting for the entire page to be rendered. This can greatly enhance user experience, especially on large or data-heavy pages.

### **How to Enable Streaming**:
- You can enable streaming by appending `?stream=true` to any route in your application. For example:
```bash
http://localhost:3000/?stream=true
```
This tells the server to stream the content progressively.

### **Key Use Cases**:
- **Progressive Loading**: Streaming is useful when building dashboards, reporting tools, or any application that fetches large amounts of data from APIs.
- **Heavy Components**: When rendering complex or data-heavy components, streaming ensures users see content as soon as it’s ready.

### **Benefits**:
- **Faster Rendering**: Parts of the page are sent to the client as they become available, improving perceived performance.
- **Enhanced User Experience**: Users can start interacting with the page without waiting for all components to load.

---

### **3. Hot Reloading (Development Mode)**

Hot reloading allows you to make changes to your code and immediately see those changes reflected in the browser without restarting the server. This speeds up development by allowing real-time feedback on code updates.

### **How to Enable Hot Reloading**:
To enable hot reloading, run the following command:
```bash
npm run dev
```

### **Key Use Cases**:
- **Fast Development**: Hot reloading is ideal when you are actively working on features, components, or layouts and need to see changes instantly without restarting the server.

### **Benefits**:
- **Instant Feedback**: No need to restart the server manually—changes are applied in real-time.
- **Improved Productivity**: Focus on writing code without interruptions caused by server restarts.

---

### **4. Component-Based Architecture**

Folonite.js is built around a **component-based architecture**, where you can define reusable pieces of UI (components) that can be shared across different pages. This allows for better maintainability, reusability, and scalability of your application.

### **How to Create Components**:
Simply create your components inside the `src/components/` directory. Here’s an example:
```javascript
// src/components/Button.js
export default function Button({ label }) {
  return `<button>${label}</button>`;
}
```

### **Key Use Cases**:
- **Modular UI**: Ideal for building reusable components like forms, buttons, and navigation bars that can be used across multiple pages.
- **Collaborative Development**: Multiple developers can work on different components without conflicts.

### **Benefits**:
- **Reusability**: Components can be reused across different parts of the application, making development faster.
- **Modularity**: Makes your application easier to maintain, as components are encapsulated.

---

### **5. Built-in External Component Marketplace**

Folonite.js includes a built-in **external component marketplace**, allowing you to download, share, and manage components directly from a GitHub repository. This simplifies the process of adding new features to your project and allows for a collaborative environment.

### **How to Use the Marketplace**:
- **Search for a component**:
```bash
npm run marketplace -- search navbar
```
- **Download a component**:
```bash
npm run marketplace -- download [componentName]
```

### **Key Use Cases**:
- **Quick UI Prototyping**: Download pre-built components like navigation bars, forms, and buttons to speed up development.
- **Share Components Globally**: Upload your custom components to the marketplace and share them with other developers.

### **Benefits**:
- **Time Savings**: Quickly download and integrate pre-built components.
- **Collaboration**: Share your components and templates with the global developer community.

---

### **6. Advanced CLI (Command-Line Interface)**

Folonite.js includes a powerful CLI that allows you to perform various tasks related to project management. The CLI offers commands for checking versions, installing dependencies, cleaning project directories, and managing components from the marketplace.

### **Key CLI Commands**:
- **Check Folonite.js version**:
```bash
npm run folonite --version
```
- **Install project dependencies**:
```bash
npm run folonite -- dependencies
```
- **Check for outdated dependencies**:
```bash
npm run folonite -- outdated
```
- **Clean `node_modules` and reinstall dependencies**:
```bash
npm run folonite -- clean
```
- **Clear npm cache**:
```bash
npm run folonite -- cache
```

### **Benefits**:
- **Streamlined Development**: Manage your project efficiently through the command line.
- **Automated Tasks**: Automatically check for outdated dependencies, clean the project directory, and reinstall necessary packages.

---

### **7. Auto Dependency Management**

Folonite.js simplifies dependency management by automatically installing required packages and keeping them updated. This reduces the need for manual dependency management and ensures your project is always using compatible versions of its dependencies.

### **How to Install Dependencies**:
To install project dependencies, simply run:
```bash
npm run folonite -- dependencies
```

### **Benefits**:
- **Hassle-Free Management**: Dependencies are installed and updated automatically.
- **Consistency**: Ensures that your project dependencies are always up-to-date and compatible.

---

### **8. API Handling with JSON Parsing and Authentication**

Folonite.js makes it easy to handle **API routes** and **JSON request bodies**. It also offers an optional **authentication middleware** that you can enable for secure routes.

### **How to Handle APIs**:
- To parse JSON request bodies, Folonite.js has the following code already available in `server.js`:
```javascript
app.use(express.json());
```

- **Optional Authentication Middleware**:
In your `server.js`, you’ll find a global authentication middleware that is **commented out by default**. If you want to use it, simply **uncomment** the code to enable authentication for your API routes:
```javascript
// Uncomment this section to enable global authentication
/*
app.use((req, res, next) => {
  const auth = req.headers.authorization;
  if (auth === 'Bearer mysecrettoken') {
    next(); // Authorized
  } else {
    res.status(401).send('Unauthorized');
  }
});
*/
```

### **How to Use API Routes**:
Folonite.js comes with built-in support for handling API routes. You can create, fetch, and manage products (or any data) via the following example routes:
```javascript
app.get('/api/products', getProducts); // Fetch products
app.post('/api/products', createProduct); // Create a new product
```

### **Benefits**:
- **Secure Your APIs**: Use authentication to protect sensitive routes.
- **Easily Parse JSON Requests**: Folonite.js includes built-in support for parsing JSON request bodies, making it easy to handle form submissions and API requests.

---

### **Conclusion**

Folonite.js is designed to be a lightweight yet powerful framework, offering **dynamic SSR**, **streaming**, **hot reloading**, and **a component-based architecture**. With the **advanced CLI**, external marketplace integration, and built-in API handling, Folonite.js is perfect for developers who want a flexible framework that scales with their project’s needs.

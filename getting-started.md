### Getting Started with Folonite.js

Welcome to **Folonite.js**, a dynamic, full-stack web framework designed for developers who need both flexibility and power. With built-in SSR, streaming, and an external marketplace, Folonite.js is ideal for developers looking to streamline their web projects. This section will guide you through setting up Folonite.js quickly.

#### Requirements
To get started, ensure that you have the following requirements installed:
- **Node.js** (version 14.x or higher)
- **npm** (version 6.x or higher)

#### Installation
Install Folonite.js globally via npm with a simple command:

```bash
npm install folonite.js
```

#### Starting a Project
After installing Folonite.js, you can create and start a project easily. Since Folonite.js doesn't require an `init` command or essential project structure creation, you can directly start working with it.

To start the development server, use the following command:

```bash
npm run dev
```

This will start the server in development mode and enable hot-reloading for a smoother development experience.

For production, you can start the server using:

```bash
npm start
```

#### External Marketplace
Folonite.js connects to an external marketplace where you can browse and install components, templates, or project starters. The marketplace is hosted on GitHub: [Folonite-Lib](https://github.com/FFFSTANZA/Folonite-Lib.git). You can use our powerful CLI to install components or templates from the marketplace. 

Examples:
```bash
npm run marketplace -- search navbar
npm run marketplace -- info navbar
npm run marketplace -- download navbar
```

#### Core Commands
Here are a few key commands to use with Folonite.js:

- **Check Folonite.js Version**:  
  ```bash
  npm run folonite version
  ```
- **Install Dependencies**:  
  ```bash
  npm run folonite -- dependencies
  ```
- **Check for Outdated Dependencies**:  
  ```bash
  npm run folonite -- outdated
  ```
- **Clean Node Modules & Reinstall**:  
  ```bash
  npm run folonite -- clean
  ```
- **Clear npm Cache**:  
  ```bash
  npm run folonite -- cache
  ```

---

That's it! You're now ready to build powerful web applications using **Folonite.js**. Continue to the [Features](#features) or [Tutorial](#tutorial) section for more in-depth examples.


### Getting Started with Folonite.js

Welcome to **Folonite.js**, a dynamic, full-stack web framework designed for developers who need both flexibility and power. With built-in SSR, streaming, and an external marketplace, Folonite.js is ideal for developers looking to streamline their web projects. This section will guide you through setting up Folonite.js quickly.

#### Requirements
To get started, ensure that you have the following requirements installed:
- **Node.js** (version 14.x or higher)
- **npm** (version 6.x or higher)

---

## Installation

### Install via npm

To install **Folonite.js** using npm, run the following command:

```bash
npm install folonite.js
```

This will install the **Folonite.js** package inside the `node_modules/` directory.

#### Transfer the Package

After installation, transfer the **Folonite.js** package to your working directory:

1. Navigate to the `node_modules/folonite.js` folder:

```bash
cd node_modules/folonite.js
```

2. Copy or move the **Folonite.js** package to your project directory:

```bash
cp -r . ../../your-project-directory/
```

Alternatively, move the package:

```bash
mv ./node_modules/folonite.js ./your-project-directory/
```

3. After transferring, initialize your project:

```bash
npm init
```

---

### Install via GitHub

You can also clone the **Folonite.js** repository directly from GitHub:

1. Clone the **Folonite.js** repository:

```bash
git clone https://github.com/FFFSTANZA/folonite.js.git
```

2. Navigate to the project directory:

```bash
cd folonite.js
```

3. Install dependencies:

```bash
npm install
```

4. Once installed, run the following to start the server:

```bash
npm start
```
Both methods will set up **Folonite.js** in your project, and you'll be ready to start building with it!

---



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


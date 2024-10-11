### Detailed Folonite.js Projects

Below are the three detailed projects, progressing from a simple To-Do list to a more advanced E-commerce application. Each project builds upon the core features of **Folonite.js**: SSR, dynamic components, and a powerful CLI. We’ve also added additional features to each project to further showcase the potential of Folonite.js.

---

### **Project 1: Enhanced To-Do List with Filtering & Task Prioritization (Beginner Level)**

In this project, we’ll enhance the basic **To-Do List** by adding task prioritization and filtering features. Users can prioritize tasks, mark them as done, and filter based on task status.

#### Step 1: Project Setup

Ensure Folonite.js is installed:

```bash
npm install folonite.js
```

Create the project structure:

```bash
mkdir src/components src/pages
```

---

#### Step 2: Create Components

**Task Component:**

Create `Task.js` in `src/components/`:

```bash
// src/components/Task.js
export default function Task({ name, completed, priority }) {
  const priorityStyle = priority === 'high' ? 'color: red;' : priority === 'medium' ? 'color: orange;' : 'color: green;';
  return `<li style="${priorityStyle} text-decoration: ${completed ? 'line-through' : 'none'};">
            ${name} (Priority: ${priority})
          </li>`;
}
```

---

#### Step 3: Create Pages

**Homepage (Task List Page):**

Create `home.js` in `src/pages/`:

```bash
// src/pages/home.js
let tasks = [
  { name: 'Buy groceries', completed: false, priority: 'medium' },
  { name: 'Read a book', completed: true, priority: 'low' },
  { name: 'Finish project', completed: false, priority: 'high' },
];

// Filter by task status
function filterTasks(status) {
  if (status === 'completed') {
    return tasks.filter(task => task.completed);
  } else if (status === 'pending') {
    return tasks.filter(task => !task.completed);
  }
  return tasks;
}

export default function Home({ filter = 'all' }) {
  const filteredTasks = filterTasks(filter);
  const taskList = filteredTasks.map(task => `<Component name="Task" props='${JSON.stringify(task)}' />`).join('');

  return `
    <div>
      <h1>To-Do List</h1>
      <form>
        <label for="filter">Filter Tasks:</label>
        <select id="filter" name="filter">
          <option value="all" ${filter === 'all' ? 'selected' : ''}>All</option>
          <option value="completed" ${filter === 'completed' ? 'selected' : ''}>Completed</option>
          <option value="pending" ${filter === 'pending' ? 'selected' : ''}>Pending</option>
        </select>
        <button type="submit">Apply</button>
      </form>
      <ul>${taskList}</ul>
    </div>
  `;
}
```

**Key Features:**

- **Task Prioritization**: Users can view tasks prioritized as "high", "medium", or "low".
- **Task Filtering**: Users can filter tasks by "completed" or "pending".

---

#### Step 4: Start the Server

Start the server:

```bash
npm start
```

Visit the app: [http://localhost:3000/](http://localhost:3000/)

This enhanced **To-Do List** demonstrates the power of **Folonite.js** to handle dynamic data and filtering in a lightweight, flexible manner.

---

### **Project 2: Movie Review App with Ratings and Search (Intermediate Level)**

We’ll build a **Movie Review App** that allows users to search for movies, view their ratings, and add new reviews.

#### Step 1: Project Setup

Ensure Folonite.js is installed:

```bash
npm install folonite.js
```

Create the project structure:

```bash
mkdir src/components src/pages
```

---

#### Step 2: Create Components

**Movie Component:**

Create `Movie.js` in `src/components/`:

```bash
// src/components/Movie.js
export default function Movie({ title, year, rating }) {
  return `<li>${title} (${year}) - Rating: ${rating}/10</li>`;
}
```

---

#### Step 3: Create Pages

**Movie List Page with Search:**

Create `home.js` in `src/pages/`:

```bash
// src/pages/home.js
const movies = [
  { title: 'Inception', year: 2010, rating: 8.8 },
  { title: 'Interstellar', year: 2014, rating: 8.6 },
  { title: 'The Dark Knight', year: 2008, rating: 9.0 },
];

// Search for movies
function searchMovies(query) {
  return movies.filter(movie => movie.title.toLowerCase().includes(query.toLowerCase()));
}

export default function Home({ search = '' }) {
  const filteredMovies = search ? searchMovies(search) : movies;
  const movieList = filteredMovies.map(movie => `<Component name="Movie" props='${JSON.stringify(movie)}' />`).join('');

  return `
    <div>
      <h1>Movie Reviews</h1>
      <form method="GET">
        <label for="search">Search Movies:</label>
        <input type="text" id="search" name="search" value="${search}" />
        <button type="submit">Search</button>
      </form>
      <ul>${movieList}</ul>
    </div>
  `;
}
```

---

**Add Movie Review Page:**

Create `add-movie.js` in `src/pages/`:

```bash
// src/pages/add-movie.js
export default function AddMovie() {
  return `
    <div>
      <h1>Add a New Movie</h1>
      <form method="POST">
        <label for="title">Title:</label>
        <input type="text" id="title" name="title" required />
        <br />
        <label for="year">Year:</label>
        <input type="number" id="year" name="year" required />
        <br />
        <label for="rating">Rating:</label>
        <input type="number" id="rating" name="rating" max="10" min="0" required />
        <br />
        <button type="submit">Add Movie</button>
      </form>
    </div>
  `;
}
```

---

#### Step 4: Add Search and Dynamic Reviews

Users can search for movies by name, and we dynamically render the search results or full movie list.

**Key Features:**

- **Movie Ratings**: Each movie has a rating.
- **Search**: Users can search for movies.
- **Add Reviews**: Users can add new reviews dynamically (in-memory).

---

#### Step 5: Start the Server

Start the server:

```bash
npm start
```

Visit the app: [http://localhost:3000/](http://localhost:3000/)

This **Movie Review App** highlights how to manage and filter dynamic content, with search functionality and the ability to add new reviews.

---

### **Project 3: E-Commerce Platform with Shopping Cart and Checkout (Advanced Level)**

In this advanced project, we’ll build a **Full E-Commerce Platform** where users can browse products, add items to a cart, and proceed to checkout. This project demonstrates dynamic product listings, cart management, and checkout handling using **Folonite.js**.

---

### **Step 1: Project Setup**

Ensure **Folonite.js** is installed:

```bash
npm install folonite.js
```

Create the project structure:

```bash
mkdir src/components
mkdir src/pages
```

---

### **Step 2: Create Components**

#### **Product Component:**

Create `Product.js` in `src/components/`:

```bash
// src/components/Product.js
export default function Product({ id, name, price }) {
  return `
    <div class="product">
      <h2>${name}</h2>
      <p>Price: $${price}</p>
      <form method="POST" action="/cart/add">
        <input type="hidden" name="id" value="${id}" />
        <button type="submit">Add to Cart</button>
      </form>
    </div>
  `;
}
```

---

#### **CartItem Component:**

Create `CartItem.js` in `src/components/`:

```bash
// src/components/CartItem.js
export default function CartItem({ name, price, quantity }) {
  return `
    <div class="cart-item">
      <h3>${name}</h3>
      <p>Quantity: ${quantity} - Price: $${price}</p>
    </div>
  `;
}
```

---

### **Step 3: Create Pages**

#### **Product List Page:**

Create `products.js` in `src/pages/`:

```bash
// src/pages/products.js
const products = [
  { id: 1, name: 'Laptop', price: 999 },
  { id: 2, name: 'Smartphone', price: 499 },
  { id: 3, name: 'Headphones', price: 199 },
];

export default function Products() {
  const productList = products.map(product => `<Component name="Product" props='${JSON.stringify(product)}' />`).join('');

  return `
    <div>
      <h1>Products</h1>
      <div class="product-list">${productList}</div>
    </div>
  `;
}
```

---

#### **Shopping Cart Page:**

Create `cart.js` in `src/pages/`:

```bash
// src/pages/cart.js
let cart = [
  { name: 'Laptop', price: 999, quantity: 1 },
  { name: 'Smartphone', price: 499, quantity: 2 },
];

export default function Cart() {
  const cartItems = cart.map(item => `<Component name="CartItem" props='${JSON.stringify(item)}' />`).join('');
  const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);

  return `
    <div>
      <h1>Shopping Cart</h1>
      <div class="cart-items">${cartItems}</div>
      <p>Total: $${total}</p>
      <form method="POST" action="/checkout">
        <button type="submit">Proceed to Checkout</button>
      </form>
    </div>
  `;
}
```

---

#### **Checkout Page:**

Create `checkout.js` in `src/pages/`:

```bash
// src/pages/checkout.js
export default function Checkout() {
  return `
    <div>
      <h1>Checkout</h1>
      <form method="POST" action="/complete-order">
        <label for="address">Shipping Address:</label>
        <input type="text" id="address" name="address" required />
        <br />
        <label for="payment">Payment Method:</label>
        <select id="payment" name="payment">
          <option value="credit">Credit Card</option>
          <option value="paypal">PayPal</option>
        </select>
        <br />
        <button type="submit">Complete Order</button>
      </form>
    </div>
  `;
}
```

---

### **Step 4: Handling Cart Management and Checkout**

#### **Add to Cart:**

Add logic to handle adding products to the cart. In **Folonite.js**, we’ll handle form submission and routing directly in the server. Modify the server to handle cart operations.

---

### **Step 5: Start the Server**

Start the server:

```bash
npm start
```

Visit the following routes:

- **Product List**: [http://localhost:3000/products](http://localhost:3000/products)
- **Shopping Cart**: [http://localhost:3000/cart](http://localhost:3000/cart)
- **Checkout**: [http://localhost:3000/checkout](http://localhost:3000/checkout)

---

### **Key Features in the Advanced E-Commerce Project:**

- **Dynamic Product Listings**: Products are dynamically loaded from a list, showing their names and prices.
- **Cart Management**: Users can add items to their shopping cart, and the cart’s total is updated in real time.
- **Checkout Process**: A simple checkout form allows users to enter shipping and payment details.
- **Form Handling**: The forms for adding items to the cart and proceeding to checkout are dynamically generated and handled via the server.

---

### **Additional Enhancements to Explore:**

1. **User Authentication**: Add a login system to keep track of user-specific carts.
2. **Payment Integration**: Simulate integrating payment options like **Stripe** or **PayPal**.
3. **Order History**: Implement an order history page where users can view their past purchases.

---

### **Final Summary**

The **E-Commerce Platform** project showcases how **Folonite.js** can handle real-time data interaction, dynamic routing, and form management in a full-fledged application.
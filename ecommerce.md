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

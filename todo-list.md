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

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

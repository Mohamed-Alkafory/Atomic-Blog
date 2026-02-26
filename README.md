<div align="center">
  <h1>⚛️ The Atomic Blog</h1>
  <p>A fast, responsive React application showcasing powerful state management with the Context API.</p>

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/React-18-blue.svg?logo=react" alt="React 18" />
    <img src="https://img.shields.io/badge/State-Context_API-green.svg" alt="Context API" />
    <img src="https://img.shields.io/badge/Data-Faker.js-pink.svg" alt="Faker.js" />
  </p>
</div>

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [Under the Hood](#-under-the-hood)
- [Getting Started](#-getting-started)
- [Technologies Used](#-technologies-used)

---

## 🌟 About the Project

**The Atomic Blog** is designed to demonstrate advanced concepts in React, specifically overcoming the hurdles of prop-drilling through the elegant implementation of the **Context API**. The application allows users to seamlessly view, search, and add blog posts in real-time while handling a massive archive of simulated data.

### 🚀 Recent Updates: Context API Refactoring

This project has recently evolved! We've overhauled the global state management. Previously, state and handler functions (`posts`, `searchQuery`, `onAddPost`, `onClearPosts`) were extensively prop-drilled down through multiple component layers. By introducing `PostProvider.js` and a custom `usePost` hook, the global state is now centrally managed.

This makes the codebase significantly cleaner, highly maintainable, and completely eliminates the annoyance of prop drilling!

---

## ✨ Key Features

- **Global State Management:** Clean and efficient state handling across the entire app using React Context API.
- **Lightning-Fast Search:** Filter dynamically through displayed posts in real-time based on their title and body content.
- **Create Your Own Posts:** A simple, interactive form to quickly add your own atomic posts to the main feed.
- **Massive Post Archive:** Explore an auto-generated archive of _10,000 simulated posts_! Easily select and promote any archive post to your active main feed.
- **Fake Dark Mode:** A lightweight theme toggle seamlessly switching between light and dark modes via a dynamic CSS class on the HTML root element.

---

## 🧠 Under the Hood

### Custom Hook (`usePost`)

Any component requiring access to the state or actions simply consumes the context using `const { ... } = usePost()`.

### Performance Optimizations

To handle the generation of 10,000 archive posts without crashing the application on every render, the project utilizes an initialization lazy-state function within `useState`. This ensures the heavy lifting of generating fake data happens exactly _once_ during the initial component mount:

```javascript
// 💥 State initialized with a callback to avoid re-running intensive array creation
const [posts] = useState(() =>
  Array.from({ length: 10000 }, () => createRandomPost()),
);
```

---

## 📦 Getting Started

### Prerequisites

Ensure you have [Node.js](https://nodejs.org/) and [NPM](https://www.npmjs.com/) installed on your local machine.

### Installation

1. **Clone the repository** to your local machine (or extract the project files).

2. **Navigate** into the project directory (if applicable):

   ```bash
   cd atomic-blog
   ```

3. **Install dependencies**:

   ```bash
   npm install
   ```

4. **Start the local development server**:

   ```bash
   npm start
   ```

5. **Open** [http://localhost:3000](http://localhost:3000) to view it in your browser.

---

## 🛠️ Technologies Used

| Technology          | Description                                                                                                              |
| :------------------ | :----------------------------------------------------------------------------------------------------------------------- |
| **React 18**        | Functional components, modern Hooks (`useState`, `useEffect`), and advanced state tools (`createContext`, `useContext`). |
| **@faker-js/faker** | Extensively used to generate realistic, random fake data (post titles, content bodies) during development.               |
| **Standard CSS**    | For elegant styling and functional Dark Mode variable handling.                                                          |

---

<div align="center">
  <p>Built with ❤️ and ⚛️ by The Atomic Blog Team.</p>
</div>

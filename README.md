# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

## Command

1. `npm create vite@latest` - Create New React Project
2. `npm install`
3. `npm run dev`

# React Project Structure

## 📁 Root Directory

my-react-app/ ├── 📁 public/  
│ ├── index.html  
│ └── favicon.ico  
├── 📁 src/  
│ ├── 📁 assets/ # Images, fonts, and other static assets  
│ ├── 📁 components/ # Reusable UI components  
│ ├── 📁 features/ # Feature-specific components and logic  
│ ├── 📁 pages/ # Top-level page components  
│ ├── 📁 layouts/ # Layout components (Header, Sidebar, etc.)  
│ ├── 📁 routes/ # React Router setup and route configs  
│ ├── 📁 hooks/ # Custom hooks  
│ ├── 📁 contexts/ # React Contexts for global state  
│ ├── 📁 services/ # API calls and service logic  
│ ├── 📁 utils/ # Utility/helper functions  
│ ├── 📁 constants/ # Constants and config  
│ ├── App.jsx # Main App component  
│ ├── main.jsx # Entry point for the React app  
│ └── index.css # Global styles  
├── .gitignore  
├── package.json  
├── README.md  
└── vite.config.js / webpack.config.js

## 🧩 Feature Folder Example (Inside `features/`)

features/ └── auth/ ├── Login.jsx ├── Register.jsx ├── authSlice.js # Redux or Zustand state slice └── authAPI.js # API integration

## 🔧 Optional Enhancements

- `tests/` - For test files if separated from component folders.
- `i18n/` - For internationalization.
- `store/` - If using Redux or Zustand and want centralized state management.

---

## ✅ Tips

- Keep components small and focused.
- Name files and folders consistently (`camelCase`, `PascalCase`, or `kebab-case`).
- Co-locate files that change together (e.g., component + styles + tests).

## 1. ✅ Ensure Source Maps Are Enabled

### For Create React App:

Source maps are enabled by default in development.

If you're using a custom setup or Vite, check `vite.config.js`:

```js
export default defineConfig({
  build: {
    sourcemap: true,
  },
});
```

# Component Styles in React

In React, component styles define how your UI components look.  
There are several main ways to style components:



## 1. Inline Styles

Directly adding style as an object inside the component.

```jsx
function Button() {
  return (
    <button
      style={{ backgroundColor: "blue", color: "white", padding: "10px" }}
    >
      Click Me
    </button>
  );
}
```

##  2. CSS Stylesheets (Plain CSS Files)
Create a .css file and import it into the component.

```css
.button {
  background-color: blue;
  color: white;
  padding: 10px;
}

```

```jsx
import './Button.css';

function Button() {
  return <button className="button">Click Me</button>;
}
```

## 3. CSS Modules
Scoped CSS to avoid class name conflicts.

Button.module.css

```css 
.button {
  background-color: blue;
  color: white;
  padding: 10px;
}
```

Button.jsx
```jsx
import styles from './Button.module.css';

function Button() {
  return <button className={styles.button}>Click Me</button>;
}
```

## 4. Tailwind CSS

Utility-first CSS framework using classes in JSX.

```jsx
function Button() {
  return (
    <button className="bg-blue-500 text-white py-2 px-4 rounded">
      Click Me
    </button>
  );
}
```
# Project Documentation: React + TypeScript + Tailwind CSS Setup

This document provides a step-by-step guide to setting up a new React project using TypeScript and Tailwind CSS for styling. 

## Table of Contents

1. [Project Prerequisites](#project-prerequisites)
2. [Initialize the Project](#initialize-the-project)
3. [Install Tailwind CSS](#install-tailwind-css)
4. [Configure Tailwind CSS](#configure-tailwind-css)
5. [Set Up Folder Structure](#set-up-folder-structure)
6. [Add Tailwind to CSS](#add-tailwind-to-css)
7. [Run the Project](#run-the-project)
8. [Project Structure](#project-structure)
9. [Usage Example](#usage-example)
10. [Optional Setup: JIT Mode for Tailwind CSS](#optional-setup-jit-mode-for-tailwind-css)

---

## 1. Project Prerequisites

- **Node.js** and **npm** installed on your system.
- Basic knowledge of React, TypeScript, and Tailwind CSS.

## 2. Initialize the Project

Create a new React project with TypeScript:

```bash
npx create-react-app my-app --template typescript
cd my-app
```

## 3. Install Tailwind CSS

Install Tailwind CSS along with PostCSS and Autoprefixer:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

## 4. Configure Tailwind CSS

Open `tailwind.config.js` and configure the `content` paths so Tailwind can find all relevant files in your project:

```js
// tailwind.config.js

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}", // Enables Tailwind for all JSX and TSX files in src
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

## 5. Set Up Folder Structure

For a clean organization, create a folder structure as follows:

```
src
├── components
│   └── ExampleComponent.tsx
├── pages
│   └── HomePage.tsx
├── hooks
│   └── useCustomHook.ts
├── styles
│   └── index.css
└── App.tsx
```

## 6. Add Tailwind to CSS

In your main CSS file (`src/styles/index.css`), add the Tailwind CSS directives:

```css
/* src/styles/index.css */

@tailwind base;
@tailwind components;
@tailwind utilities;
```

Then, make sure this CSS file is imported into your app, typically in `src/index.tsx`:

```typescript
// src/index.tsx

import React from 'react';
import ReactDOM from 'react-dom';
import './styles/index.css'; // Tailwind CSS import
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

## 7. Run the Project

To start the development server and see Tailwind in action, run:

```bash
npm start
```

## 8. Project Structure

With Tailwind CSS set up, here’s a recommended file structure:

```
my-app
├── public
└── src
    ├── components
    ├── hooks
    ├── pages
    ├── styles
    │   └── index.css
    ├── App.tsx
    ├── index.tsx
    └── tailwind.config.js
```

## 9. Usage Example

Here’s a quick example of a React component that uses Tailwind classes.

```tsx
// src/components/ExampleComponent.tsx

import React from 'react';

const ExampleComponent: React.FC = () => {
  return (
    <div className="flex items-center justify-center h-screen bg-gray-100">
      <h1 className="text-4xl font-bold text-blue-500">
        Welcome to React + TypeScript + Tailwind CSS!
      </h1>
    </div>
  );
};

export default ExampleComponent;
```

## 10. Optional Setup: JIT Mode for Tailwind CSS

Just-In-Time (JIT) mode makes your builds faster and produces smaller CSS files by generating styles as you use them. To enable JIT mode, modify `tailwind.config.js`:

```js
// tailwind.config.js

/** @type {import('tailwindcss').Config} */
module.exports = {
  mode: 'jit', // Enables JIT mode
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

---

This completes the initial setup of React, TypeScript, and Tailwind CSS. You’re ready to start building your project!

## Practical No. 5

## Practical 5A - Install and configure React Router in the React application.

**Aim:** - React Routing &amp; Data Handling.

### a) Install and configure React Router in the React application.

Requirements:

- VS Code

- Node.js

- React application created using vite

Create a React Application

Steps

1. Open VS Code

2. Open Terminal → New Terminal.

3. Type this commands in Terminal.

i. npm create vite@latest react-routing ii. npm intall react-router-dom@6

In src/App.jsx

```jsx
import React from "react";
import {
  BrowserRouter as Router,
  Routes,
  Route,
  Link
} from "react-router-dom";
function Home() {
  return (
    <div>
      <h2>Home Page</h2>
    </div>
  );
}
function About() {
  return (
    <div>
      <h2>About Page</h2>
      <ul>
        <li>
          <Link to="/team">Our Team</Link>
        </li>
        <li>
          <Link to="/company">Our Company</Link>
        </li>
      </ul>
    </div>
  );
}
function Team() {
  return <h2>Team Page</h2>;
}
function Company() {
  return <h2>Company Page</h2>;
}
function Contact() {
  return <h2>Contact Page</h2>;
}
function App() {
  return (
    <Router>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/about">About</Link>
          </li>
          <li>
            <Link to="/contact">Contact</Link>
          </li>
        </ul>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/team" element={<Team />} />
        <Route path="/company" element={<Company />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </Router>
  );
}
export default App;
```

In src/index.css

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
}
h1 {
    text-align: center;
    color: red;
}
nav ul {
    display: flex;
    justify-content: center;
    list-style: none;
}
nav li {
    margin: 0 10px;
}
nav a {
    text-decoration: none;
    color: #333;
}
button {
    display: block;
    margin: 20px auto;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    cursor: pointer;
}
button:hover {
    background-color: blue;
}
```

**Output:-**

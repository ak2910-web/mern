## Practical No. 3

## Practical 3A - Create a React application using Vite/CRA and display "Welcome to MERN Stack Development".

**Aim:** - React Introduction and JSX.

### a) Create a React application using Vite/CRA and display "Welcome to MERN Stack Development".

Requirements:

- Visual Studio Code

- Node.js and npm

- React

- Vite

- Web Browser

#### 1. Open Command Prompt / VS Code Terminal

#### 2. Run command:

```bash
npm create vite@latest my-app
```

Select Framework – react

Select Variant – JavaScript

Which linear to use? – ESLint

Install with npm and start now? – Yes

#### 3.

Open this folder in VS Code

#### 4. Go to src folder -> Open App.jsx

Delete all existing code and write this:

```jsx
import React from "react";
import "./App.css";
function App()
{
  return(
    <div className="container">
      <h1>Welcome to MERN Stack Development</h1>
    </div>
  )
}
export default App;
```

#### 5. Open App.css

Delete all existing code and write this:

```css
.container{
  text-align: center;
  margin-top: 50 px;
}
h1{
  color: red;
}
```

#### 6. Run in the Terminal:

```bash
npm run dev
```

Open link http://localhost:5174 in Browser

**7. Output**

## Practical No. 3

## Practical 3D - Apply Basic css styling to React Component.

**Aim:** - React Introduction and JSX.

### d) Apply Basic css styling to React Component.

In src/App.jsx

```jsx
import React from "react";
import "./App.css";
function App()
{
  return(
    <div className="container">
      <h1>Welcome to React Js</h1>
      <p>This component is styled using Css</p>
      <button>Click Me</button>
    </div>
  );
}
export default App;
```

In src/App.css

```css
.container{
  text-align: center;
  margin-top: 50 px;
  font-family: Arial, Helvetica, sans-serif;
}
h1{
  color: blue;
}
p{
  color: green;
}
button{
  background-color: blue;
  color: white;
  padding: 10 px, 20 px;
  border: none;
  cursor: pointer;
}
button:hover{
  background-color: blue;
}
```

**Output:**

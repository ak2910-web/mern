## Practical No. 3

## Practical 3C - Write a program to declare variables and writw a function to calculate sum of 2 numbers and display results.

**Aim:** - React Introduction and JSX.

### c) Write a program to declare variables and writw a function to calculate sum of 2 numbers and display results.

In src/App.jsx

```jsx
import React from "react";
import "./App.css";
function App()
{
  const num1=20;
  const num2=30;
  function calculateSum(a,b){
    return a+b;
  }
  return(
    <div>
      <h1>React-Sum of two numbers</h1>
      <p>First Number:{num1}</p>
      <p>Second Number:{num2}</p>
      <h2>Sum={calculateSum(num1,num2)}</h2>
    </div>
  );
}
export default App;
```

In src/App.css

```css
div{
  text-align: center;
  margin-top: 50 px;
  font-family: Arial, Helvetica, sans-serif;
}
h1{
  color: blue;
}
h2{
  color: green;
}
```

**Output:**

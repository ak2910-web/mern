## Practical No. 4

## Practical 4C - Use the useState hook to manage and update data.

**Aim:** - React Components, Props, and State.

### c) Use the useState hook to manage and update data.

(Hook :- It is a special function that allows you to use react features such as state and lifecycle)

useState:- Built-in react features that lets you to add local state to functional components.

It returns and array with the current state value and setter function to update that value and trigger a component re-render.

In src/App.jsx

```jsx
import React, { useState } from "react";
function App(){
const[name,setName]=useState("Vaishnavi");
const updateName=()=>{
    setName("Hello");
  };
  return(
    <div>
      <h2>useState hook Example</h2>
      <h3>{name}</h3>
      <button onClick={updateName}>Update data</button>
    </div>
  );
}
export default App;
```

**Output:-**

When we click Update data:

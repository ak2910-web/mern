## Practical No. 3

## Practical 3E - Create a simple functional component and render in App.jsx.

**Aim:** - React Introduction and JSX.

### e) Create a simple functional component and render in App.jsx.

#### 1. Create Page Components

Inside the Src folder, create a folder

Inside it, create:

Student.jsx

In src/Student.jsx

```jsx
import React from "react";
function Student(){
    return(
        <div>
            <h2>Student Component</h2>
            <p>Name:Vaishnavi</p>
            <p>Class:T.Y.IT</p>
        </div>
    );
}
export default Student;
```

In src/App.jsx

```jsx
import React from "react";
import Student from "./Student";
function App()
{
  return(
    <div className="container">
      <h1>Simple Functional Component</h1>
      <Student/>
    </div>
  );
}
export default App;
Output:
```

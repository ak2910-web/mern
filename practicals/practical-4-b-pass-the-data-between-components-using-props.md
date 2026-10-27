## Practical No. 4

## Practical 4B - Pass the data between components using Props.

**Aim:** - React Components, Props, and State.

### b) Pass the data between components using Props.

In src/App.jsx

```jsx
import React from "react";
import Employee from "./Employee";
function App(){
  return(
    <div>
      <Employee name="Vaishnavi" department="IT" salary={50000}/>
    </div>
  );
}
export default App;
```

In src/Employee.jsx

```jsx
function Employee(props){
    return(
        <div>
            <h2>Employee Details</h2>
            <p>Name:{props.name}</p>
            <p>Department:{props.department}</p>
            <p>Salary:{props.salary}</p>
        </div>
    );
}
export default Employee;
```

**Output:-**

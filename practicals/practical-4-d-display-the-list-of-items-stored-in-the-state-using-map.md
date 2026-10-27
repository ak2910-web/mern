## Practical No. 4

## Practical 4D - Display the list of items stored in the state using map( ).

**Aim:** - React Components, Props, and State.

### d) Display the list of items stored in the state using map( ).

map( ):- Map function is used to Dynamically loop through an array and render a list of JSX

elements.

In src/App.jsx

```jsx
import React from "react";
function App() {
    const employees = [
        {
            id: 1,
            name: "Vaishnavi",
            dept: "IT",
        },
        {
            id: 2,
            name: "Sneha",
            dept: "CS",
        },
        {
            id: 3,
            name: "Veer",
            dept: "CS",
        },
        {
            id: 4,
            name: "Geeta",
            dept: "HR",
        }
    ];
    return (
        <div>
            <h2>Employee details</h2>
            <table border="1" cellPadding="10">
                <thead>
                    <tr>
                        <th>ID</th>
                        <th>Name</th>
                        <th>Dept</th>
                    </tr>
                </thead>
                <tbody>
                    {
                        employees.map((employee) => (
                            <tr key={employee.id}>
                                <td>{employee.id}</td>
                                <td>{employee.name}</td>
                                <td>{employee.dept}</td>
                            </tr>
                        ))
                    }
                </tbody>
            </table>
        </div>
    );
}
export default App;
Output:-
```

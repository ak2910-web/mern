## Practical No. 2

## Practical 2F - Implement a small JavaScript program combining functions, arrays and Objects.

**Aim:** - Core JavaScript Concept for MERN.

### f) Implement a small JavaScript program combining functions, arrays and Objects.

#### 1. Add JavaScript Code.

```js
const employees = [
    {
        empID: 101,
        name: "Vaishnavi",
        department: "IT",
        salary: 50000
    },
    {
        empID: 102,
        name: "Neha",
        department: "HR",
        salary: 45000
    },
    {
        empID: 103,
        name: "Gita",
        department: "Finance",
        salary: 40000
    }
];
function displayEmployee(employeeList) {
    console.log("--- Employee Details ---");
    employeeList.forEach(function(employee) {
               console.log("Employee ID:", employee.empID);
            console.log("Name:", employee.name);
            console.log("Department:", employee.department);
            console.log("Salary:", employee.salary);
            console.log(" ------------- ");
             });
}
function calculateTotalSalary(employeeList) {
            let totalSalary = 0;
            employeeList.forEach(function(employee) {
                        totalSalary += employee.salary;
            });
            console.log("Total Salary =", totalSalary);
}
displayEmployee(employees);
calculateTotalSalary(employees);
```

**2.Output:-**

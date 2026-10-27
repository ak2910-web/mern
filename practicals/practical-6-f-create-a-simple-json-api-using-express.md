## Practical No. 6

## Practical 6F - Create a Simple JSON API using Express

**Aim:** - Aim: Node.js and Express Fundamentals

### f) Create a Simple JSON API using Express

in server.js

```js
const express = require("express");
const app = express();
const PORT = 3000;
const students = [
    { id: 1, name: "Amit", course: "B.Sc. IT", semester: 5 },
    { id: 2, name: "Priya", course: "B.Sc. IT", semester: 5 },
    { id: 3, name: "Neha", course: "B.Sc. IT", semester: 5 }
];
app.get("/api/students", (req, res) => {
     res.json(students);
});
app.listen(PORT, () => {
console.log(`Server running on port ${PORT}`);
});
```

Output: http://localhost:3000/api/students

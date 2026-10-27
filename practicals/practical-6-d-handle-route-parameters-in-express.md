## Practical No. 6

## Practical 6D - Handle Route Parameters in Express

**Aim:** - Aim: Node.js and Express Fundamentals

### d) Handle Route Parameters in Express

in server.js

```jsx
const express = require("express");
const app = express();
const PORT = 3000;
app.get("/student/:name/:rollno", (req, res) => {
      const studentName = req.params.name;
      const rollNo = req.params.rollno;
      res.send(`
        <h1>Student Information</h1>
        <p>Name: ${studentName}</p>
        <p>Roll Number: ${rollNo}</p>
`);
});
app.listen(PORT, () => {
         console.log(`Server running on port ${PORT}`);
});
```

**Output:**

## Practical No. 6

## Practical 6E - Handle Query Parameters in Express

**Aim:** - Aim: Node.js and Express Fundamentals

### e) Handle Query Parameters in Express

in server.js

```jsx
const express = require("express");
const app = express();
const PORT = 3000;
app.get("/student", (req, res) => {
        const name = req.query.name;
        const course = req.query.course;
        res.send(`
          <h1>Student Details</h1>
          <p>Name: ${name}</p>
          <p>Course: ${course}</p>
        `);
});
app.listen(PORT, () => {
      console.log(`Server running on port ${PORT}`);
});
```

Output: http://localhost:3000/student?name=Siya&course=BScIT

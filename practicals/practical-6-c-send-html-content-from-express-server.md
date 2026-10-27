## Practical No. 6

## Practical 6C - Send HTML Content from Express Server

**Aim:** - Aim: Node.js and Express Fundamentals

### c) Send HTML Content from Express Server

Procedure:

Create a route that sends HTML content in server.js

```jsx
const express = require("express");
const app = express();
const PORT = 3000;
app.get("/", (req, res) => {
res.send(`
     <h1>MERN Stack Development</h1>
     <h2>Backend Using Express.js</h2>
     <p>Welcome to the Express server</p>
     <p>Course: B.Sc. Information Technology</p>
     <p>Semester: V</p>
  `);
});
app.listen(PORT, () => {
     console.log(`Server running on port ${PORT}`);
});
```

open local host:3000

**Output:**

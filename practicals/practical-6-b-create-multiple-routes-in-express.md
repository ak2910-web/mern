## Practical No. 6

## Practical 6B - Create Multiple Routes in Express

**Aim:** - Aim: Node.js and Express Fundamentals

### b) Create Multiple Routes in Express

Procedure:

Create multiple routes like /, /about, /courses, /contact in server.js

```js
const express = require("express");
const app = express();
const PORT = 3000;
app.get("/", (req, res) => {
    res.send("Welcome to the Home Page");
});
app.get("/about", (req, res) => {
    res.send("About MERN Stack Development");
});
app.get("/courses", (req, res) => {
  res.send("Course: B.Sc. Information Technology");
});
app.get("/contact", (req, res) => {
  res.send("Contact: mern@example.com");
});
app.listen(PORT, () => {
console.log(`Server running on port ${PORT}`);
});
```

run the server.

```bash
Node server.js
```

Open the URLs individually in browser to see output.

**Output:**

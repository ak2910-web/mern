## Practical No. 8

## Practical 8A - Create a MongoDB Scheme and model using Mongoose.

**Aim:** - Aim: API Creation and Integration

### a) Create a MongoDB Scheme and model using Mongoose.

Procedure

1. Open the Practical-3 folder in Visual Studio Code.

2 Open the integrated terminal and initialize the project.

```bash
npm init –y
```

3 Install the required packages.

```bash
npm install express mongoose
```

#### 4. Create a file named

Server.js

```js
const express = require("express");
const mongoose = require("mongoose");
const app = express();
app.use(express.json());
```

mongoose

.connect("mongodb://127.0.0.1:27017/studentDB")

```js
  .then(() => console.log("MongoDB Connected Successfully"))
  .catch((err) => console.log(err));
const studentSchema = new mongoose.Schema({
  name: String,
  course: String,
  semester: Number,
  city: String,
});
const Student = mongoose.model("Student", studentSchema);
app.listen(3000, () => {
  console.log("Server Running on Port 3000");
});
```

Run

>node server.js

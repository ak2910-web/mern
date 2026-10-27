## Practical No. 9

## Practical 9A - Create the React Frontend and connect it with Express.

**Aim:** - Aim: Frontend and Backend Integration using React and Axios.

### a) Create the React Frontend and connect it with Express.

To create a React application and connect it to the Express backend using Axios.Procedure

1: Keep the Backend Server Ready

Open the existing Practical_7 folder in one VS Code window.

Make sure the backend server.js contains the CRUD API developed in Practical 7.

Install CORS in the backend folder:

```bash
npm install cors
```

Add this line near the top of server.js:

```js
const cors = require("cors");
```

Add the following middleware after creating the Express application:

```js
app.use(cors());
app.use(express.json());
```

The beginning of the backend file should appear as follows:

```js
const express = require("express");
const mongoose = require("mongoose");
const cors=require("cors");
const app = express();
app.use(cors())
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

Run the Backend: node server.js

#### 2. Create the React Application

Open another VS Code window.

Create a folder named: Practical-9

Open the terminal and execute: npm create vite@latest

Enter the project name: student-frontend

Select:

Framework: React

Variant: JavaScript

Then execute: cd student-frontend

```bash
npm install
```

Vite provides a quick way to create a React project using a React template. (vitejs)

#### 3. Install Axios

Inside the student-frontend folder,

run: npm install axios

Axios is a promise-based HTTP client used to send requests such as GET, POST, PUT, and DELETE. (npm)

4: Start the React Application

Execute: npm run dev

Open the displayed local URL: http://localhost:51734/

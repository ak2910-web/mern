## Practical No. 8

## Practical 8B - Implement REST API Operations.

**Aim:** - Aim: API Creation and Integration

### b) Implement REST API Operations.

In server.js

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
// POST
app.post("/students", async (req, res) => {
  const student = new Student(req.body);
  await student.save();
  res.json(student);
});
// GET
app.get("/students", async (req, res) => {
  const students = await Student.find();
  res.json(students);
});
// PUT
app.put("/students/:id", async (req, res) => {
  const student = await Student.findByIdAndUpdate(req.params.id, req.body, {
    new: true,
  });
  res.json(student);
});
// DELETE
app.delete("/students/:id", async (req, res) => {
  await Student.findByIdAndDelete(req.params.id);
  res.json({
    message: "Student Deleted Successfully",
  });
});
app.listen(3000, () => {
  console.log("Server Running on Port 3000");
});
```

**Output:**

Execute: node server.js

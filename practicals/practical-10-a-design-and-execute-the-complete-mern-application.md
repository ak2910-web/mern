## Practical No. 10

## Practical 10A - Design and Execute the Complete MERN Application.

**Aim:** - Aim: Complete MERN CRUD Application.

### a) Design and Execute the Complete MERN Application.

To organize and execute the complete MERN application using separate frontend and backend folders.

Steps:

Create a folder named: Practical-10

Inside it maintain the following structure:

#### 1. Create the Backend Folder

Open the backend folder in Visual Studio Code and initialize the Node.js project:

```bash
npm init –y
```

Install the required packages: npm install express mongoose cors

2: Create server.js

Server.js

```js
const express = require("express");
const mongoose = require("mongoose");
const cors = require("cors");
const app = express();
const PORT = 3000;
app.use(cors());
app.use(express.json());
```

mongoose

.connect("mongodb://127.0.0.1:27017/studentDB")

```js
  .then(() => {
    console.log("MongoDB Connected Successfully");
  })
  .catch((error) => {
    console.log("MongoDB Connection Error:", error);
  });
const studentSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
  },
  course: {
    type: String,
    required: true,
  },
  semester: {
    type: Number,
    required: true,
  },
  city: {
    type: String,
    required: true,
  },
});
const Student = mongoose.model("Student", studentSchema);
// CREATE Student
app.post("/students", async (req, res) => {
  try {
    const student = new Student(req.body);
    const savedStudent = await student.save();
    res.status(201).json(savedStudent);
  } catch (error) {
    res.status(400).json({
      message: "Unable to add student",
      error: error.message,
    });
  }
});
// READ All Students
app.get("/students", async (req, res) => {
try {
    const students = await Student.find();
    res.json(students);
  } catch (error) {
    res.status(500).json({
      message: "Unable to retrieve students",
    });
  }
});
// UPDATE Student
app.put("/students/:id", async (req, res) => {
  try {
    const updatedStudent = await Student.findByIdAndUpdate(
      req.params.id,
      req.body,
      {
        new: true,
        runValidators: true,
      },
    );
    res.json(updatedStudent);
  } catch (error) {
    res.status(400).json({
      message: "Unable to update student",
      error: error.message,
    });
  }
});
// DELETE Student
app.delete("/students/:id", async (req, res) => {
  try {
    await Student.findByIdAndDelete(req.params.id);
    res.json({
      message: "Student Deleted Successfully",
    });
  } catch (error) {
    res.status(400).json({
      message: "Unable to delete student",
    });
  }
});
app.listen(PORT, () => {
  console.log(`Server Running on Port ${PORT}`);
});
```

#### 3. Create the React Frontend

Open another terminal inside the Practica-10 folder and execute:

```bash
npm create vite@latest frontend
```

Select:

Framework: React

Variant: JavaScript

When asked: Install with npm and start now?

Select: Yes

In App.jsx

```jsx
import { useEffect, useState } from "react";
import "./App.css";
const apiUrl = "http://localhost:3000/students";
async function request(url, options = {}) {
  const response = await fetch(url, {
    headers: { "Content-Type": "application/json" },
    ...options,
  });
  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }
  return response.json();
}
function App() {
  const [students, setStudents] = useState([]);
  const [formData, setFormData] = useState({
  name: "",
    course: "",
    semester: "",
    city: "",
  });
  const [editingId, setEditingId] = useState(null);
  const fetchStudents = async () => {
    const data = await request(apiUrl);
    setStudents(data);
  };
```

useEffect(() => {

```js
const loadStudents = async () => {
  try {
    await fetchStudents();
  } catch (error) {
    console.error("Unable to load students:", error);
  }
};
loadStudents();
```

}, []);

```js
const handleChange = (event) => {
  setFormData({ ...formData, [event.target.name]: event.target.value });
};
const handleSubmit = async (event) => {
```

event.preventDefault();

```jsx
  try {
    if (editingId) {
      await request(`${apiUrl}/${editingId}`, {
        method: "PUT",
        body: JSON.stringify(formData),
      });
      setEditingId(null);
    } else {
      await request(apiUrl, {
        method: "POST",
        body: JSON.stringify(formData),
      });
    }
    setFormData({ name: "", course: "", semester: "", city: "" });
    await fetchStudents();
  } catch (error) {
    console.error("Unable to save student:", error);
  }
};
const handleEdit = (student) => {
  setFormData({
    name: student.name,
    course: student.course,
    semester: student.semester,
    city: student.city,
  });
  setEditingId(student._id);
};
const handleDelete = async (id) => {
  try {
    await request(`${apiUrl}/${id}`, { method: "DELETE" });
    await fetchStudents();
  } catch (error) {
    console.error("Unable to delete student:", error);
  }
};
return (
  <div className="main-bg">
    <header className="top-header">
      MERN Student Management System
      <span>React + Express + MongoDB</span>
    </header>
    <div className="dashboard">
      <h2>Complete MERN Application Dashboard</h2>
      <div className="stats">
        <div className="stat-box">
          <p>Total Students</p>
          <h3>{students.length}</h3>
        </div>
        <div className="stat-box">
          <p>Active Semester</p>
          <h3>5</h3>
        </div>
        <div className="stat-box">
          <p>Database Status</p>
          <h3 className="connected">Connected</h3>
        </div>
      </div>
      <form onSubmit={handleSubmit} className="dash-form">
```

<input

type="text"

name="name"

placeholder="Enter student name"

value={formData.name}

onChange={handleChange}

required

/>

<input

type="text"

name="course"

placeholder="Enter course"

value={formData.course}

onChange={handleChange}

required

/>

<input

type="number"

name="semester"

placeholder="Enter semester"

value={formData.semester}

onChange={handleChange}

required

/>

<input

type="text"

name="city"

placeholder="Enter city"

value={formData.city}

onChange={handleChange}

required

/>

```jsx
  <button type="submit" className="add-btn">
    {editingId ? "Update" : "Add Student"}
  </button>
</form>
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Course</th>
      <th>Semester</th>
      <th>City</th>
      <th>Actions</th>
    </tr>
  </thead>
  <tbody>
    {students.map((student) => (
      <tr key={student._id}>
        <td>{student.name}</td>
        <td>{student.course}</td>
        <td>{student.semester}</td>
        <td>{student.city}</td>
        <td>
```

<button

className="edit-btn"

onClick={() => handleEdit(student)}

>

Edit

```js
</button>
```

<button

className="del-btn"

onClick={() => handleDelete(student._id)}

>

Delete

```jsx
          </button>
        </td>
      </tr>
    ))}
  </tbody>
</table>
<p className="footer">
```

B.Sc. Information Technology - Full Stack Development MERN Practice

```js
        </p>
      </div>
    </div>
  );
}
export default App;
```

In App.css

body {

```css
margin: 0;
  font-family: Arial, sans-serif;
  background: #eef1f5;
}
.main-bg {
  min-height: 100vh;
}
.top-header {
  background: #1a1a2e;
  color: white;
  padding: 12px 25px;
  font-weight: bold;
  display: flex;
  justify-content: space-between;
}
.top-header span {
  font-size: 12px;
  color: #aaa;
}
.dashboard {
  width: 90%;
  max-width: 1000px;
  background: white;
  margin: 20px auto;
  padding: 25px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.dashboard h2 {
  margin-top: 0;
}
.stats {
  display: flex;
  gap: 15px;
  margin: 20px 0;
}
.stat-box {
  flex: 1;
  background: #f8f9fa;
  padding: 15px;
  border-radius: 8px;
  border: 1px solid #eee;
}
.stat-box p {
  margin: 0;
  font-size: 12px;
  color: #666;
}
.stat-box h3 {
  margin: 5px 0 0 0;
  font-size: 20px;
}
.connected {
  color: #1a1a2e;
}
.dash-form {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 20px;
}
.dash-form input {
  padding: 8px 10px;
  flex: 1;
  min-width: 130px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
.add-btn {
  background: #1a1a2e;
  color: white;
  border: none;
  padding: 8px 15px;
  border-radius: 5px;
  cursor: pointer;
}
table {
  width: 100%;
  border-collapse: collapse;
}
th {
  background: #f1f1f1;
  text-align: left;
  padding: 10px;
  font-size: 13px;
}
td {
  padding: 10px;
  border-bottom: 1px solid #eee;
  font-size: 13px;
}
.edit-btn {
  background: #6c757d;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 4px;
  margin-right: 5px;
  cursor: pointer;
}
.del-btn {
  background: #1a1a2e;
  color: white;
  border: none;
  padding: 5px 10px;
  border-radius: 4px;
  cursor: pointer;
}
.footer {
  text-align: center;
  font-size: 11px;
  color: #888;
  margin-top: 20px;
}
```

If the application does not start automatically, execute:

```bash
cd frontend
```

```bash
npm install
```

```bash
npm run dev
```

#### 4. Install Axios

Inside the frontend folder, execute: npm install axios

#### 5. Run the Backend

Open a terminal inside the backend folder:

```bash
node server.js
```

Expected terminal output:

6: Run the Frontend

Open another terminal inside the frontend folder:

```bash
npm run dev
```

Open the displayed URL: http://localhost:5173/

**Output:**

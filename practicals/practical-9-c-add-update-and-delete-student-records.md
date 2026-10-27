## Practical No. 9

## Practical 9C - Add, Update and Delete Student Records

**Aim:** Frontend and Backend Integration using React and Axios.

### Question

Create a React application that adds, edits, lists, and deletes student records through an Express API.

### `src/App.jsx`

```jsx
import { useEffect, useState } from "react";
import axios from "axios";
import "./App.css";

const apiUrl = "http://localhost:3000/students";

function App() {
  const [students, setStudents] = useState([]);
  const [formData, setFormData] = useState({
    name: "",
    course: "",
    semester: "",
    city: "",
  });
  const [editingId, setEditingId] = useState(null);
  const [message, setMessage] = useState("");

  const fetchStudents = async () => {
    try {
      const response = await axios.get(apiUrl);
      setStudents(response.data);
    } catch (error) {
      console.error("Error fetching students:", error);
    }
  };

  useEffect(() => {
    fetchStudents();
  }, []);

  const handleChange = (event) => {
    setFormData({ ...formData, [event.target.name]: event.target.value });
  };

  const handleSubmit = async (event) => {
    event.preventDefault();

    try {
      if (editingId) {
        await axios.put(`${apiUrl}/${editingId}`, formData);
        setMessage("Student updated successfully!");
        setEditingId(null);
      } else {
        await axios.post(apiUrl, formData);
        setMessage("Student added successfully!");
      }

      setFormData({ name: "", course: "", semester: "", city: "" });
      await fetchStudents();
    } catch (error) {
      console.error("Error saving student:", error);
      setMessage("Error saving student.");
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
      await axios.delete(`${apiUrl}/${id}`);
      setMessage("Student deleted successfully!");
      await fetchStudents();
    } catch (error) {
      console.error("Error deleting student:", error);
      setMessage("Error deleting student.");
    }
  };

  return (
    <div className="container">
      <h1>Student Management System</h1>
      {message && <p className="message">{message}</p>}

      <form onSubmit={handleSubmit}>
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
        <button type="submit">
          {editingId ? "Update Student" : "Add Student"}
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
                <button onClick={() => handleEdit(student)}>Edit</button>
                <button onClick={() => handleDelete(student._id)}>
                  Delete
                </button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}

export default App;
```

### `src/App.css`

```css
body {
  font-family: Arial, sans-serif;
  background: #f4f4f4;
  margin: 0;
}

.container {
  width: 85%;
  margin: 30px auto;
  background: white;
  padding: 25px;
  border-radius: 8px;
}

h1 {
  text-align: center;
}

.message {
  color: green;
  text-align: center;
  font-weight: bold;
}

form {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  margin-bottom: 25px;
}

input {
  padding: 10px;
  flex: 1;
  min-width: 160px;
}

button {
  padding: 10px 15px;
  margin: 3px;
  cursor: pointer;
}

table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  border: 1px solid #cccccc;
  padding: 10px;
  text-align: left;
}

th {
  background: #eeeeee;
}
```

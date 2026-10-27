## Practical No. 9

## Practical 9B - Retrieve and Display Student Records.

**Aim:** - Aim: Frontend and Backend Integration using React and Axios.

### b) Retrieve and Display Student Records.

To retrieve student records from the Express backend and display them in a React application.

In App.jsx

```jsx
import { useEffect, useState } from "react";
import axios from "axios";
import "./App.css";
function App() {
  const [students, setStudents] = useState([]);
  const fetchStudents = async () => {
    try {
      const response = await axios.get("http://localhost:3000/students");
      setStudents(response.data);
    } catch (error) {
      console.error("Error fetching students:", error);
    }
  };
  useEffect(() => {
    fetchStudents();
  }, []);
  return (
    <div className="container">
      <h1>Student Management System</h1>
      <h2>Student Records Retrieved from Backend</h2>
      <table>
        <thead>
          <tr>
            <th>Name</th>
            <th>Course</th>
            <th>Semester</th>
            <th>City</th>
          </tr>
        </thead>
        <tbody>
          {students.map((student) => (
            <tr key={student._id}>
              <td>{student.name}</td>
              <td>{student.course}</td>
              <td>{student.semester}</td>
              <td>{student.city}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}
export default App;
```

In App.css

body {

```css
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  margin: 0;
}
.container {
  width: 80%;
  margin: 40px auto;
  background-color: white;
  padding: 25px;
  border-radius: 8px;
}
h1 {
  text-align: center;
}
table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}
```

th,

td {

```css
  border: 1px solid #cccccc;
  padding: 12px;
  text-align: left;
}
th {
  background-color: #eeeeee;
}
```

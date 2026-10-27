## Practical No. 3

## Practical 3B - Display dynamic data using JSX.

**Aim:** - React Introduction and JSX.

### b) Display dynamic data using JSX.

In src/App.jsx

```jsx
import React from "react";
import "./App.css";
function App()
{
  const student_name="Vaishnavi";
  const rollno=101;
  const course="T.Y.BSc IT";
  const subject="React JS";
  const marks=90;
  return(
    <div className="container">
      <h1>Display Dynamic Data Using JSX</h1>
      <h2>Student Information</h2>
      <p><b>Name:</b>{student_name}</p>
      <p><b>Roll no:</b>{rollno}</p>
      <p><b>Course:</b>{course}</p>
      <p><b>Subject:</b>{subject}</p>
      <p><b>Marks:</b>{marks}</p>
      <h3>Status:{marks>=35? "Pass":"Fail"}</h3>
    </div>
  );
}
export default App;
```

In src/App.css

```css
.container{
  width: 450 px;
  margin: 50 px auto;
  background: white;
  padding: 20 px;
  border-radius: 10 px;
  box-shadow: 0 0 10 px gray;
}
h1{
  color: blue;
  text-align: center;
}
h2{
  color: green;
}
```

**Output:**

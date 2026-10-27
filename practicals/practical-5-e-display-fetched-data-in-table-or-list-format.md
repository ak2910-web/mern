## Practical No. 5

## Practical 5E - Display fetched data in table or list format.

**Aim:** - React Routing &amp; Data Handling.

### e) Display fetched data in table or list format.

In src/App.jsx

```jsx
import { useEffect, useState } from "react";
import axios from "axios";
import "./App.css";
function App() {
  const [users, setUsers] = useState([]);
  useEffect(() => {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => {
        setUsers(response.data);
      })
      .catch((error) => {
        console.error("Unable to retrieve users:", error);
      });
  }, []);
  return (
    <div className="container">
      <h1>User Information</h1>
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Username</th>
            <th>Email</th>
            <th>City</th>
          </tr>
        </thead>
        <tbody>
          {users.map((user) => (
            <tr key={user.id}>
              <td>{user.id}</td>
              <td>{user.name}</td>
              <td>{user.username}</td>
              <td>{user.email}</td>
              <td>{user.address.city}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  );
}
export default App;
```

In src/App.css

```css
.container {
  width: 90%;
  margin: 30px auto;
  text-align: center;
}
table {
  width: 100%;
  border-collapse: collapse;
}
th,
td {
  border: 1px solid black;
  padding: 10px;
  text-align: left;
}
th {
  background-color: lightgray;
}
```

**Output:-**

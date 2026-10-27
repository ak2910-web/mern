## Practical No. 5

## Practical 5F - Implement search or filter functionality on displayed data.

**Aim:** - React Routing &amp; Data Handling.

### f) Implement search or filter functionality on displayed data.

In src/App.jsx

```jsx
import { useEffect, useState } from "react";
import axios from "axios";
import "./App.css";
function App() {
  const [users, setUsers] = useState([]);
  const [searchText, setSearchText] = useState("");
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
  const filteredUsers = users.filter((user) =>
    user.name.toLowerCase().includes(searchText.toLowerCase())
  );
  return (
    <div className="container">
      <h1>Search User</h1>
      <input
        type="text"
        placeholder="Enter user name"
        value={searchText}
        onChange={(event) => setSearchText(event.target.value)}
      />
      <table>
        <thead>
          <tr>
            <th>Name</th>
            <th>Email</th>
            <th>City</th>
          </tr>
        </thead>
        <tbody>
          {filteredUsers.map((user) => (
            <tr key={user.id}>
              <td>{user.name}</td>
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
  width: 85%;
  margin: 30px auto;
  text-align: center;
}
input {
  width: 300px;
  padding: 10px;
  margin-bottom: 20px;
  font-size: 16px;
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

## Module-2

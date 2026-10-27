## Practical No. 4

## Practical 4E - Create a form component to accept user input and display it dynamically.

**Aim:** - React Components, Props, and State.

### e) Create a form component to accept user input and display it dynamically.

In src/App.jsx

```jsx
import { useState } from "react";
function App() {
    const [name, setName] = useState("");
    const [email, setEmail] = useState("");
    const [course, setCourse] = useState("");
    const [submitted, setSubmitted] = useState(false);
    const handleSubmit = (e) => {
        e.preventDefault();
        setSubmitted(true);
    };
    return (
        <div>
            <h2>User Registration Form</h2>
            <form onSubmit={handleSubmit}>
                <label>Name:</label>
                <input
                    type="text"
                    value={name}
                    onChange={(e) =>
                        setName(e.target.value)
                    }
                />
                <br /><br />
                <label>Email:</label>
                <input
                    type="email"
                    value={email}
                    onChange={(e) =>
                        setEmail(e.target.value)
                    }
                />
                <br /><br />
                <label>Course:</label>
                <input
                    type="text"
                    value={course}
                    onChange={(e) =>
                        setCourse(e.target.value)
                    }
                />
                <br /><br />
                <button type="submit">Submit</button>
            </form>
            {submitted && (
                <div>
                    <h3>Entered Details</h3>
                    <p>Name: {name}</p>
                    <p>Email: {email}</p>
                    <p>Course: {course}</p>
                </div>
            )}
        </div>
    );
}
export default App;
```

**Output:-**

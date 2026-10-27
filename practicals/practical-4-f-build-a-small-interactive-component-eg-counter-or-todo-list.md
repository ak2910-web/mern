## Practical No. 4

## Practical 4F - Build a small interactive component (Eg., Counter or ToDo list).

**Aim:** - React Components, Props, and State.

### f) Build a small interactive component (Eg., Counter or ToDo list).

In src/App.jsx

```jsx
import { useState } from "react";
function App() {
    const [task, setTask] = useState("");
    const [tasks, setTasks] = useState([]);
    const addTask = () => {
        if (task.trim() === "") {
            alert("Please enter a task");
            return;
        }
        setTasks([
            ...tasks,
            {
                id: Date.now(),
                name: task,
                completed: false
            }
        ]);
        setTask("");
    };
    const deleteTask = (id) => {
        setTasks(tasks.filter((item) => item.id !== id));
    };
    const completeTask = (id) => {
        setTasks(
            tasks.map((item) =>
                item.id === id
                    ? { ...item, completed: !item.completed }
                    : item
            )
        );
    };
    return (
        <div>
            <h2>My To-Do List</h2>
            <input
                type="text"
                placeholder="Enter a task"
                value={task}
                onChange={(e) => setTask(e.target.value)}
            />
            <button onClick={addTask}>Add Task</button>
            <h3>Tasks</h3>
            {tasks.length === 0 ? (
                <p>No task added yet</p>
            ) : (
                <ul>
                    {tasks.map((item) => (
                        <li key={item.id}>
                            <span
                                onClick={() => completeTask(item.id)}
                                style={{
                                    textDecoration: item.completed
                                        ? "line-through"
                                        : "none",
                                    cursor: "pointer"
                                }}
                            >
                                {item.name}
                            </span>
                            <button
                                onClick={() => deleteTask(item.id)}
                            >
                                Delete
                            </button>
                        </li>
                    ))}
                </ul>
            )}
        </div>
    );
}
export default App;
Output:-
```

## Practical No. 3

## Practical 3F - Create a React component that display current Date and Time Dynamically using JavaScript.

**Aim:** - React Introduction and JSX.

### f) Create a React component that display current Date and Time Dynamically using JavaScript.

#### 1. Create Page Components

Inside the Src folder, create a folder

Inside it, create:

DateTime.jsx

In src/ DateTime.jsx

```jsx
import React, {useState, useEffect} from "react";
function Datetime(){
const [datetime, setDatetime] = useState(new Date());
useEffect(() => {
    const timer = setInterval(() => {
        setDatetime(new Date());
    }, 1000);
    return () => clearInterval(timer);
}, []);
return (
    <div style={{ textAlign: "center", marginTop: "20px" }}>
        <h2>Current Date and Time</h2>
        <h3>Date:{datetime.toLocaleDateString()}</h3>
        <h3>Time: {datetime.toLocaleTimeString()}</h3>
    </div>
);
}
export default Datetime;
```

In src/ App.jsx

```jsx
import React from "react";
import Datetime from "./DateTime";
function App(){
  return(
    <div>
      <Datetime/>
    </div>
  );
}
export default App;
Output:-
```

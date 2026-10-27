## Practical No. 4

## Practical 4A - Create a multiple components and render them on a single page.

**Aim:** - React Components, Props, and State.

### a) Create a multiple components and render them on a single page.

Requirements:

- VS Code

- Node.js

- React + Vite

#### 1. Create a new React project using

```bash
npm create vite@latest practical-4 ----- template react
```

#### 2. Go inside folder:

```bash
cd practical-4
```

3. install dependencies: npm install

In src/Header.jsx

```jsx
function Header(){
    return(
        <div>
            <h1>MERN Practical</h1>
            <hr/>
        </div>
    );
}
export default Header;
```

In src/Student.jsx

```jsx
function Student(props){
    return(
        <div>
            <h3>Student Information</h3>
            <p>Name:{props.name}</p>
            <p>Class:{props.className}</p>
            <p>Roll No:{props.rollno}</p>
            <hr/>
        </div>
    );
}
export default Student;
```

In src/Footer.jsx

```jsx
function Footer(){
    return(
        <div>
            <h4>BNN College, Bhiwandi</h4>
            <p>React Practical</p>
        </div>
    );
}
export default Footer;
```

In src/Counter.jsx

```jsx
import { useState } from "react";
function Counter(){
    const [count,setCount]=useState(0);
    return(
        <div>
            <h3>Counter using State</h3>
            <h2>{count}</h2>
            <button onClick={()=>setCount(count+1)}></button>
            <button onClick={()=>setCount(count-1)}></button>
            <hr/>
        </div>
    );
}
export default Counter;
```

In src/App.jsx

```jsx
import Header from "./Header";
import Student from "./Student";
import Counter from "./Counter";
import Footer from "./Footer";
function App(){
  return(
    <div style={{textAlign:"center"}}>
      <Header/>
      <Student name="Vaishnavi" className="TYIT" rollno="50"/>
      <Counter/>
      <Footer/>
    </div>
  );
}
export default App;
```

**Output:-**

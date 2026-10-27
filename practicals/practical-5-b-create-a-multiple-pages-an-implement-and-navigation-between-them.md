## Practical No. 5

## Practical 5B - Create a multiple pages an implement and navigation between them.

**Aim:** - React Routing &amp; Data Handling.

### b) Create a multiple pages an implement and navigation between them.

In src/Home.jsx

```jsx
function Home() {
    return (
        <div>
            <h2>Welcome to Sunrise Public School</h2>
            <p>
                Welcome to Sunrise public school we provide
                quality education to students
            </p>
            <h3>School News</h3>
            <p>
                Admissions are open for the academic year
                2026-2027
            </p>
        </div>
    );
}
export default Home;
```

In src/About.jsx

```jsx
function About() {
    return (
        <div>
            <h2>About Our School</h2>
            <p>
                Sunrise public school was established in 1995.
                Our school provides education from primary to
                secondary level.
            </p>
            <p>
                Welcome, we focus on academics, sports, cultural
                activities and overall development of students.
            </p>
        </div>
    );
}
export default About;
```

In src/Classes.jsx

```jsx
function Classes() {
    return (
        <div>
            <h2>Classes</h2>
            <ul>
                <li>Class 1</li>
                <li>Class 2</li>
                <li>Class 3</li>
                <li>Class 4</li>
            </ul>
        </div>
    );
}
export default Classes;
```

In src/Teachers.jsx

```jsx
function Teachers() {
    return (
        <div>
            <h2>Our Teachers</h2>
            <table border="1">
                <thead>
                    <tr>
                        <th>Teacher Name</th>
                        <th>Subject</th>
                        <th>Class</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>ABC</td>
                        <td>Maths</td>
                        <td>9th</td>
                    </tr>
                    <tr>
                        <td>DDR</td>
                        <td>Science</td>
                        <td>9th</td>
                    </tr>
                    <tr>
                        <td>XYZ</td>
                        <td>English</td>
                        <td>10th</td>
                    </tr>
                </tbody>
            </table>
        </div>
    );
}
export default Teachers;
```

In src/Contact.jsx

```jsx
function Contact() {
    return (
        <div>
            <h2>Contact Us</h2>
            <p>
                <b>School:</b> Sunrise Public School
            </p>
            <p>
                <b>Address:</b> Mumbai, Maharashtra
            </p>
            <p>
                <b>Email:</b> Sunrise@gmail.com
            </p>
            <p>
                <b>Phone:</b> 987654321
            </p>
        </div>
    );
}
export default Contact;
```

In src/App.jsx

```jsx
import React from "react";
import {
    BrowserRouter as Router,
    Routes,
    Route,
    Link
}
from "react-router-dom";
import Home from "./Home";
import About from "./About";
import Classes from "./Classes";
import Teachers from "./Teachers";
import Contact from "./Contact";
function App() {
    return (
        <Router>
            <nav>
                <Link to="/">Home</Link>{"  "}
                <Link to="/about">About</Link>{"  "}
                <Link to="/classes">Classes</Link>{"  "}
                <Link to="/teachers">Teachers</Link>{"  "}
                <Link to="/contact">Contact</Link>{"  "}
            </nav>
            <Routes>
                <Route path="/" element={<Home />} />
                <Route path="/about" element={<About />} />
                <Route path="/classes" element={<Classes />} />
                <Route path="/teachers" element={<Teachers />} />
                <Route path="/contact" element={<Contact />} />
            </Routes>
        </Router>
    );
}
export default App;
```

**Output:-**

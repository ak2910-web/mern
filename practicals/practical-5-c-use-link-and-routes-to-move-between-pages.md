## Practical No. 5

## Practical 5C - Use Link and Routes to move between pages.

**Aim:** - React Routing &amp; Data Handling.

### c) Use Link and Routes to move between pages.

In src/Services.jsx

```jsx
function Services()
{
     return (
         <div>
            <h2>Our Services</h2>
             <ul>
                <li>Web Application Development</li>
                 <li>Database Management</li>
                  <li>API Development</li>
            </ul>
        </div>
    );
}
export default Services;
```

In src/Contact.jsx

```jsx
function Contact()
 {
    return (
         <div>
             <h2>Contact Us</h2>
              <p>Email: support@example.com</p>
               <p>Phone: 9876543210</p>
        </div>
    );
}
export default Contact;
```

In src/App.jsx

```jsx
import { Routes, Route, Link } from "react-router-dom";
import Services from "./Services.jsx";
import Contact from "./Contact.jsx";
  function App()
   {
    return (
       <div>
        <h1>MERN Service Portal</h1>
         <nav>
          <Link to="/">Home</Link> |{" "}
          <Link to="/services">Services</Link> |{" "}
          <Link to="/contact">Contact</Link>
        </nav>
        <hr />
          <Routes>
            <Route path="/" element={<h2>Welcome to Our Website</h2>} />
            <Route path="/services" element={<Services />} />
            <Route path="/contact" element={<Contact />} />
          </Routes>
    </div>
  );
}
export default App;
Output:-
```

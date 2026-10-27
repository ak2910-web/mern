## Practical No. 5

## Practical 5D - Fetch data from public API using Axios.

**Aim:** - React Routing &amp; Data Handling.

### d) Fetch data from public API using Axios.

Axios:- Axios is a popular promised based Http client for JavaScript. It is commonly used to

make API request in browser and node.js.

To install the Axios we used the command:

```bash
npm install axios
```

```bash
npm start
```

In src/App.jsx

```jsx
import React, { useEffect, useState } from "react";
import axios from "axios";
function App() {
    const [products, setProducts] = useState([]);
    useEffect(() => {
        axios.get("https://dummyjson.com/products")
            .then((response) => {
                setProducts(response.data.products);
            })
            .catch((error) => {
                console.log(error);
            });
    }, []);
    return (
        <div>
            <h1>Product Details</h1>
            <table border="1" cellPadding="10">
                <thead>
                    <tr>
                        <th>ID</th>
                        <th>Product Name</th>
                        <th>Price</th>
                        <th>Category</th>
                        <th>Rating</th>
                    </tr>
                </thead>
                <tbody>
                    {products.map((product) => (
                        <tr key={product.id}>
                            <td>{product.id}</td>
                            <td>{product.title}</td>
                            <td>{product.price}</td>
                            <td>{product.category}</td>
                            <td>{product.rating}</td>
                        </tr>
                    ))}
                </tbody>
            </table>
        </div>
    );
}
export default App;
Output:-
```

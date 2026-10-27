## Practical No. 6

## Practical 6A - Install Express and create a simple server.

**Aim:** - Aim: Node.js and Express Fundamentals

### a) Install Express and create a simple server.

Procedure Since this is the first Express practical, the initial project setup and Express installation will be explained step by step.

1: Create the Practical Folder

Inside the MERN Practicals folder, create a new folder named: Practical-1. Open this folder in Visual Studio Code.

2: Open the Integrated Terminal

Select: Terminal -> New Terminal

The terminal should display a path similar to:

```bash
PS D:\MERN_Practicals\Practical-6>
```

3 : Initialize the Node.js Project

Execute the init command in the terminal.

This command creates a package.json file containing the basic information and dependencies of the Node.js project.

4: Install Express.js

Execute

The install command for express.(npm install express)

After successful installation, Express will be added to the project dependencies.

5: Create the Server File

Create a new file named: server.js

The project structure will appear similar to:

Practical-6 containing

node_modules

package-lock.json

package.json

server.js

6: Write the Express Server Program

Open server.js and enter the server program.

```js
const express = require("express");
const app = express();
const PORT = 3000;
app.get("/", (req, res) => {
res.send("Welcome to MERN Stack Backend Development");
});
app.listen(PORT, () => {
console.log(`Server running on port ${PORT}`);
});
```

7: Run the Server

Save the file and execute the file using node.

```bash
Node server.js
```

The terminal displays: Server is running on port 3000

8: Open the Application in the Browser

Open the following address in the browser:

http://localhost:3000

The browser displays the response sent by the Express server

**Output:**

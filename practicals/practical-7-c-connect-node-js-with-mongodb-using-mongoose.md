## Practical No. 7

## Practical 7C - Connect Node.js with MongoDB using Mongoose.

**Aim:** - Aim: Install MongoDB Community Server and MongoDB Compass.

### c) Connect Node.js with MongoDB using Mongoose.

Create a folder named MONGO

Open the integrated terminal

Bash

> Cd MONGO

>npm init –y

>npm install mongoose

Create a file inside MONGO folder named server.js

```js
const mongoose = require("mongoose");
```

mongoose

.connect("mongodb://127.0.0.1:27017/studentDB")

```js
.then(() => {
  console.log("MongoDB Connected Successfully");
})
.catch((error) => {
  console.log(error);
});
```

Run:

```bash
Node server.js
```

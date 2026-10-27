## Practical No. 2

## Practical 2C - Demonstrate the use of Arrow Function.

**Aim:** - Core JavaScript Concept for MERN.

### c) Demonstrate the use of Arrow Function.

Definition:- Arrow function is shorter way to write a function.

#### 1) Without Parameter.

#### i) Add JavaScript Code.

```js
const display=()=>
{
    console.log("Welcome to node.js");
};
display();
```

**ii) Output:-**

#### 2) One Parameter.

#### i) Add JavaScript Code.

```js
const display=(name)=>
{
    console.log("Hello",name);
};
display("Vaishnavi");
```

**ii) Output:-**

#### 3) Arrow functions with multiple parameters.

#### i) Add JavaScript Code.

```js
const add=(a,b)=>
{
    return a+b;
};
console.log("Sum=",add(10,20));
```

**ii) Output:-**

#### 4) Arrow functions with implicit return.

#### i) Add JavaScript Code.

```js
const multiply=(a,b)=>a*b;
console.log("Product=",multiply(5,6));
```

**ii) Output:-**

#### 5) Arrow function to check whether the number is Even or Odd.

#### i) Add JavaScript Code.

```js
const checkSum=(num)=>{
    if (num%2==0){
        console.log(num+" is even");
    }
    else{
        console.log(num+" is odd");
    }
}
checkSum(12);
checkSum(15);
```

**ii) Output:-**

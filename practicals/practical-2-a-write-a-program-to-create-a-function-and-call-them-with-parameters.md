## Practical No. 2

## Practical 2A - Write a program to create a function and call them with parameters.

**Aim:** - Core JavaScript Concept for MERN.

### a) Write a program to create a function and call them with parameters.

#### 1) To find whether the number is Odd or Even.

#### i) Add JavaScript Code.

```js
function checkEvenOdd(num)
{
    if (num%2==0)
    {
        console.log(num+" is even");
    }
    else
    {
        console.log(num+" is Odd");
    }
}
checkEvenOdd(12);
checkEvenOdd(7);
```

**ii) Output:-**

#### 2) To find the Area of Rectangle.

#### i) Add JavaScript Code.

```js
function rectangleArea(length,width)
{
    return length*width;
}
let area=rectangleArea(8,5);
console.log("Area of Rectangle:",area);
```

**ii) Output:-**

#### 3) To display the Student Details.

#### i) Add JavaScript Code.

```js
function stud(name,age,course)
{
    console.log("Name:",name);
    console.log("Age:",age);
    console.log("Course:",course);
}
stud("Vaishnavi",19,"MERN Stack");
```

**ii) Output:-**

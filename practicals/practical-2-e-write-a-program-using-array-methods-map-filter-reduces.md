## Practical No. 2

## Practical 2E - Write a program using Array Methods. (Map, Filter, Reduces).

**Aim:** - Core JavaScript Concept for MERN.

### e) Write a program using Array Methods. (Map, Filter, Reduces).

Map :- Map methods creates new array by applying a function to every element of original array.

Filter :- It creates a new array containing only the elements that satisfy a condition.

Reduces:- Reduces all array elements to Single Value.

#### 1. Add JavaScript Code.

```js
const numbers=[10,15,20,25,30];
const doubled=numbers.map(num=>num*2);
console.log("Doubled Array:",doubled);
const greaterthan20=numbers.filter(num=>num>20);
console.log("Numbers greater than 20:",greaterthan20);
const sum=numbers.reduce((total,num)=>total+num,0);
console.log("Sum of array elements:",sum);
```

**2. Output:-**

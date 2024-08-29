# JavaScript Array Methods Examples

This repository provides examples of common JavaScript array methods: flatMap, map, join, split, reduce, filter, and forEach. These examples cover usage with arrays, arrays of objects, and nested arrays of objects.

## Table of Contents

1. [flatMap](#flatmap)
2. [map](#map)
3. [join](#join)
4. [split](#split)
5. [reduce](#reduce)
6. [filter](#filter)
7. [forEach](#foreach)

## flatMap

The `flatMap()` method creates a new array with the results of calling a provided function on every element in the array, and then flattening the result by one level.

### Array Example

```javascript
const numbers = [1, 2, 3, 4];
const result = numbers.flatMap((x) => [x, x * 2]);
console.log(result); // [1, 2, 2, 4, 3, 6, 4, 8]
```

### Array of Objects Example

```javascript
const users = [
  { name: "John", hobbies: ["reading", "swimming"] },
  { name: "Jane", hobbies: ["painting", "running"] },
];
const allHobbies = users.flatMap((user) => user.hobbies);
console.log(allHobbies); // ['reading', 'swimming', 'painting', 'running']
```

### Nested Array of Objects Example

```javascript
const departments = [
  { name: "Engineering", employees: [{ name: "Alice" }, { name: "Bob" }] },
  { name: "Marketing", employees: [{ name: "Charlie" }, { name: "David" }] },
];
const allEmployees = departments.flatMap((dept) =>
  dept.employees.map((emp) => emp.name)
);
console.log(allEmployees); // ['Alice', 'Bob', 'Charlie', 'David']
```

## map

The `map()` method creates a new array with the results of calling a provided function on every element in the array.

### Array Example

```javascript
const numbers = [1, 2, 3, 4];
const squared = numbers.map((x) => x * x);
console.log(squared); // [1, 4, 9, 16]
```

### Array of Objects Example

```javascript
const users = [
  { name: "John", age: 30 },
  { name: "Jane", age: 28 },
];
const names = users.map((user) => user.name);
console.log(names); // ['John', 'Jane']
```

### Nested Array of Objects Example

```javascript
const departments = [
  { name: "Engineering", employees: [{ name: "Alice" }, { name: "Bob" }] },
  { name: "Marketing", employees: [{ name: "Charlie" }, { name: "David" }] },
];
const deptInfo = departments.map((dept) => ({
  name: dept.name,
  employeeCount: dept.employees.length,
}));
console.log(deptInfo);
// [
//   { name: 'Engineering', employeeCount: 2 },
//   { name: 'Marketing', employeeCount: 2 }
// ]
```

## join

The `join()` method creates and returns a new string by concatenating all of the elements in an array, separated by a specified separator string.

### Array Example

```javascript
const fruits = ["Apple", "Banana", "Orange"];
const result = fruits.join(", ");
console.log(result); // 'Apple, Banana, Orange'
```

### Array of Objects Example

```javascript
const users = [
  { name: "John", age: 30 },
  { name: "Jane", age: 28 },
];
const namesString = users.map((user) => user.name).join(" and ");
console.log(namesString); // 'John and Jane'
```

## split

The `split()` method divides a String into an ordered list of substrings, puts these substrings into an array, and returns the array.

### String Example

```javascript
const sentence = "The quick brown fox jumps over the lazy dog";
const words = sentence.split(" ");
console.log(words);
// ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog']
```

## reduce

The `reduce()` method executes a reducer function on each element of the array, resulting in a single output value.

### Array Example

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
console.log(sum); // 10
```

### Array of Objects Example

```javascript
const orders = [
  { id: 1, total: 200 },
  { id: 2, total: 300 },
  { id: 3, total: 100 },
];
const totalAmount = orders.reduce((acc, order) => acc + order.total, 0);
console.log(totalAmount); // 600
```

### Nested Array of Objects Example

```javascript
const departments = [
  { name: "Engineering", employees: [{ salary: 80000 }, { salary: 90000 }] },
  { name: "Marketing", employees: [{ salary: 70000 }, { salary: 75000 }] },
];
const totalSalary = departments.reduce(
  (acc, dept) =>
    acc + dept.employees.reduce((deptAcc, emp) => deptAcc + emp.salary, 0),
  0
);
console.log(totalSalary); // 315000
```

## filter

The `filter()` method creates a new array with all elements that pass the test implemented by the provided function.

### Array Example

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // [2, 4, 6]
```

### Array of Objects Example

```javascript
const users = [
  { name: "John", age: 30 },
  { name: "Jane", age: 28 },
  { name: "Bob", age: 35 },
];
const over30 = users.filter((user) => user.age > 30);
console.log(over30); // [{ name: 'Bob', age: 35 }]
```

### Nested Array of Objects Example

```javascript
const departments = [
  {
    name: "Engineering",
    employees: [
      { name: "Alice", exp: 5 },
      { name: "Bob", exp: 3 },
    ],
  },
  {
    name: "Marketing",
    employees: [
      { name: "Charlie", exp: 2 },
      { name: "David", exp: 4 },
    ],
  },
];
const experiencedDepts = departments.filter((dept) =>
  dept.employees.some((emp) => emp.exp > 3)
);
console.log(experiencedDepts);
// [
//   { name: 'Engineering', employees: [{ name: 'Alice', exp: 5 }, { name: 'Bob', exp: 3 }] },
//   { name: 'Marketing', employees: [{ name: 'Charlie', exp: 2 }, { name: 'David', exp: 4 }] }
// ]
```

## forEach

The `forEach()` method executes a provided function once for each array element.

### Array Example

```javascript
const numbers = [1, 2, 3, 4];
numbers.forEach((num) => console.log(num * 2));
// Output:
// 2
// 4
// 6
// 8
```

### Array of Objects Example

```javascript
const users = [
  { name: "John", age: 30 },
  { name: "Jane", age: 28 },
];
users.forEach((user) => console.log(`${user.name} is ${user.age} years old`));
// Output:
// John is 30 years old
// Jane is 28 years old
```

### Nested Array of Objects Example

```javascript
const departments = [
  { name: "Engineering", employees: [{ name: "Alice" }, { name: "Bob" }] },
  { name: "Marketing", employees: [{ name: "Charlie" }, { name: "David" }] },
];
departments.forEach((dept) => {
  console.log(`${dept.name} department:`);
  dept.employees.forEach((emp) => console.log(`- ${emp.name}`));
});
// Output:
// Engineering department:
// - Alice
// - Bob
// Marketing department:
// - Charlie
// - David
```

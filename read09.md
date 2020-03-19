# Concepts of Functional Programming in Javascript


> Functional programming is a programming paradigm — a style of building the structure and elements of computer  
> programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and 
> mutable data .

### Pure Functions
* It returns the same result if given the same arguments (it is also referred as deterministic)
* It does not cause any observable side effects
  - Examples of observable side effects include modifying a global object or a parameter passed by reference.
* Pure functions are stable, consistent, and predictable. Given the same parameters, pure functions will always return the same result. 
* Are immutability: state cannot change after it’s created.
* Are Referential transparency: will always have the same output, given the same input.

> If a function consistently yields the same result for the same input, it is referentially transparent.

`pure functions + immutable data = referential transparency`

### Example of an Pure function
`const calculateArea = (radius, pi) => radius * radius * pi;`

### Examples of an Impure function
_Simply because it uses a global object that was not passed as a **parameter** to the function._

`let PI = 3.14;`
`const calculateArea = (radius) => radius * radius * PI;`
`calculateArea(10); // returns 314.0`


**_Any function that relies on a random number generator cannot be pure._**

### Beneficts of Pure functions
* The code’s definitely easier to test

### Functions as first-class entities
* Is that functions are also treated as values and used as data.
* Functions as first-class entities can:
  - Refer to it from constants and variables
  - Pass it as a parameter to other functions
  - Return it as result from other functions

#### Example

`const sum = (a, b) => a + b;`
`const subtraction = (a, b) => a - b;`

`const doubleOperator = (f, a, b) => f(a, b) * 2;`

`doubleOperator(sum, 3, 1); // 8`
`doubleOperator(subtraction, 3, 1); // 4`

### Higher-order functions
* Is a function that either:
  - Takes one or more functions as arguments, or
  - Returns a function as its result

`const even = n => n % 2 == 0;`
`const listOfNumbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];`
`listOfNumbers.filter(even); // [0, 2, 4, 6, 8, 10]`

### Declarative approach
#### Example:

We want to filter only people over a specified value of age, in this example people who are more than 21 years old.

`let people = [`
`  { name: "TK", age: 26 },`
`  { name: "Kaio", age: 10 },`
`  { name: "Kazumi", age: 30 }`
`];`

`const olderThan21 = person => person.age > 21;`
`const overAge = people => people.filter(olderThan21);`
`overAge(people); // [{ name: 'TK', age: 26 }, { name: 'Kazumi', age: 30 }]`

### Map
The idea of map is to transform a collection.

`var people = [`
`  { name: "TK", age: 26 },`
`  { name: "Kaio", age: 10 },`
`  { name: "Kazumi", age: 30 }`
`];`


`const makeSentence = (person) => ${person.name} is ${person.age} years old;`

`const peopleSentences = (people) => people.map(makeSentence);`
  
`peopleSentences(people);`
`// ['TK is 26 years old', 'Kaio is 10 years old', 'Kazumi is 30 years old']`

### Reduce
* The idea of reduce is to receive a function and a collection, and return a value created by combining the items.

`let shoppingCart = [`
`  { productTitle: "Product 1", amount: 10 },`
`  { productTitle: "Product 2", amount: 30 },`
`  { productTitle: "Product 3", amount: 20 },`
`  { productTitle: "Product 4", amount: 60 }`
`];`

`const sumAmount = (currentTotalAmount, order) => currentTotalAmount + order.amount;`

`const getTotalAmount = (shoppingCart) => shoppingCart.reduce(sumAmount, 0);`

`getTotalAmount(shoppingCart); // 120`
# Read: 10 - The Call Stack and Debugging

> A call stack is a mechanism for an interpreter to keep track of its place in a script that calls multiple functions 
> — what function is currently being run and what functions are called from within that function, etc.

1. When a script calls a function, the interpreter adds it to the call stack and then starts carrying out the function.
1. Any functions that are called by that function are added to the call stack further up, and run where their calls are reached.
1. When the current function is finished, the interpreter takes it off the stack and resumes execution where it left off in the last code listing.
1. Delete the executed function from our call stack list


**_If the stack takes up more space than it had assigned to it, it results in a "stack overflow" error.**_

* The call stack is primarily used for function invocation (call). 
* Since the call stack is single, function(s) execution, is done, _**one at a time**_, from top to bottom. 
* It means the call stack is _**synchronous**_.

> Call stack is a data structure that uses the Last In, First Out (LIFO) principle to temporarily store and manage function invocation (call).

### LIFO
* When we say that the call stack, operates by the data structure principle of **Last In, First Out**, it means that the last function that gets pushed into the stack is the first to be pop out, when the function returns.

### Temporarily store: 
* When a function is invoked (called), the function, its parameters, and variables are pushed into the call stack to form a stack frame. This stack frame is a memory location in the stack. The memory is cleared when the function returns as it is pop out of the stack.

### Manage function invocation (call)
* The call stack maintains a record of the position of each stack frame. 
* It knows the next function to be executed (and will remove it after execution). 
* **_This is what makes code execution in JavaScript synchronous._**

> Think of yourself standing on a queue, in a grocery store cash point. You can only be attended to after the person in front of you have been attended > to. That’s synchronous.

### What causes a stack overflow?
A stack overflow occurs when there is a recursive function (a function that calls itself) **_without an exit point_**. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

## Summary on call stack 

1. It is single-threaded. Meaning it can only do one thing at a time.
2. Code execution is synchronous.
3. A function invocation creates a stack frame that occupies a temporary memory.
4. It works as a LIFO — Last In, First Out data structure.

# Types of error messages

### Reference errors
* This is as simple as when you try to use a variable that is not yet declared you get this type os errors.

`console.log(foo) // Uncaught ReferenceError: foo is not defined`
`foo = 'Hello' // Uncaught ReferenceError: foo is not defined let foo`


### Syntax errors
* This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

`JSON.parse( {'foo': 'bar'} ) // Uncaught SyntaxError: Unexpected token o in JSON at position 1`
`JSON.parse('{"foo":"bar"}')`

### Range errors
* Try to manipulate an object with some kind of length and give it an invalid length and this kind of errors will show up.

`var foo= []`
`foo.length = foo.length -1 // Uncaught RangeError: Invalid array length`
`foo.length = foo.length - 2 // (or foo.length - foo.length)`

### Type errors
* This types of errors show up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

`var foo = {}`
`foo.bar // undefined`
`foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined`

# Debugging

* To debug your JS code, the easiest and maybe the most common way its to simply console.log().
* The breakpoint can also be achieved by putting a debugger statement in your code in the line you want to break.
* To add conditional breakpoints by right-clicking a previous set breakpoint, which will make your program stop at that point only if a condition is met.

# Handling errors
* Usually try to catch the errors so we can gracefully fallback to a default state of our application in case of an error.
* The worthiest outcome of using try…catch tough is the fact that your application will keep on running, maybe with some side effects due to the fact that numberResult now contains an empty array but at least it didn’t just crash onto itself 
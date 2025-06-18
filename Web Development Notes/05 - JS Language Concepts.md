
# JavaScript
- Object oriented
- Case-sensitivie
- Prototypal inheritance
	- Dynamic inheritance: a prototype can be changed
- loosely typed
- Single threaded!
- statements optionally end in ;

## Variable Declaration
- type depends on value stored
- `let` recommended:
	- use `let` keyword
	- `let name;`
	- block scope
- constants: `const`
	- `const pi = 3.14;`
- Must be initialized when declared
- `var`
	- `var name;`
	- Hoisted: if you declare the variable later in the script, javascript assumes that it is declared at the top of the program
	- No block scope - the `var` is scoped within either global or the function
	- Problem: you can redeclare the same variable in multiple points in the program, leading to potential logic errors

## Common Operators
- Math; `+, -, /, *, **, %`
- Concatenation: `+`
- Assignment: `=`
- Comparison: `==, ===, !=, !==, >, <, <=, >=`
	- 0 == false returns true
	- 0 === false returns false
- `typeof`: type of a variable
- Modify-in-place: `+=, *=, etc`
- Increment, decrement: `++, --`
- Logic: `&&, ||, !`

## Numbers
- Integers
	- `let n = 123;`
	- have size limitations (these can be avoided using BigInt)
- Floats
	- `let n = 1.23`
	- Have size limitations
- BigInts
	- `let n = 9007199254740991n`
	- Supports arbitrary length integers
- Special Numbers:
	- `Infinity`
		- Eg: 1/0
	- `-Infinity`
		- eg. -1/0
	- `NaN`
		- Eg. `'string' * 3`

## String
- Double Quotes:
	- `"Hello, world!"`
- Single quotes:
	- `'Hello, world!'`
- Backticks:
	- \`Hello, world!\` `
	- Support string interpolation
		- You can have some variables substituted in your string
		- ![[Pasted image 20250121205651.png]]


# Objects, Collections, Iterations

## Objects
- Very flexible and powerful
- keyed collections of data

- Object Constructor syntax![[Pasted image 20250121205859.png]]
- Object literal syntax![[Pasted image 20250121205919.png]]

- Accessing properties:
	- similar to java
	- `obj.someKey`

- You can also refer to properties via square bracket notation
	- `obj['someKey']`
	- `obj['someKey'] = 4;`
	- Very useful when property names are not static 

## Arrays
- Ordered List
	- Constructor notation
	- Square bracket notation
	![[Pasted image 20250122131300.png]]
	
- Always an instance of `Array`
- `arr.length`: largest index + 1
	- It is NOT always the size of the array
	- ![[Pasted image 20250121210346.png]]
- Interesting methods:
	- `push, pop`: add, remove from end
	- `unshift, shift`: add, remove from start
	- `slice`: subsets an array
	- `join`: concatenates elements with separator
	- `concat`: merge arrays
	- `includes`: is value in array
	- `reduce`: execute callback on elements

## Other Collections
- Map
	- key-value pair, where the key can be an object
	- Overcomes limitations of objects:
		- objects only support string keys
![[Pasted image 20250121210806.png]]

- Set
	- Collection of unique values
	![[Pasted image 20250121210755.png]]

## Loops
- `while`
- `do while`
- `for`
- `for` loop on iterables (like arrays, strings, maps, sets, and other collections)
	- `for(const element of array) {`
	- for-of loop
- `for` loop on enumerables (like an Object)
	- `for(const property in object) {`
	- for-in loop


# Functions

- Function declaration:
	- same as in java
	![[Pasted image 20250121211241.png]]
- Function expression:
	- basically the same as a function, but you're assigning the value to a variable
![[Pasted image 20250121211259.png]]
- Arrow function
	- with explicit return 
	![[Pasted image 20250121211349.png]]
	- with implicit return![[Pasted image 20250121212155.png]]


- All functions are values
	- You can assign them to variables (same as java)
- All functions are Objects
	- You can assign properties to them ![[Pasted image 20250121211837.png]]
- Since functions are values and objects:
	- you can pass them as arguments to other functions
	- allows for function composition (which is kind of like a function pointer)![[Pasted image 20250121212025.png]]
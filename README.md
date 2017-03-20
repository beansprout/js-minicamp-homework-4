# Homework #4

## Instructions
---
1. Feynman Writing Prompts - Write out explanations of the following concepts like you are explaining it to a 12 year old.  Doing this will help you quickly discover any holes in your understanding.  Ask your questions on Slack.

### Callback Functions
- a function that calls another function when running.
- **Example:** `the Array.map()` method is a function that runs functions on every element of an array.

### Closure
- a closure is what makes it possible to access  variable in a function outside of a function.  In js this is frequently done by having a function reference another function.  When function1 references function2, all the variables in function1 are accessible even though they are not within the scope of function2.

**example:**

```
function say667() {
  // Local variable that ends up within closure
  var num = 42;
  var say = function() { console.log(num); }
  num++;
  return say;
}
var sayNumber = say667();
sayNumber(); // note variable is not a function, but calling a variable as a function that refers to a function is fine.  //logs 43
```

### arguments array
- The arguments array should really be called the arguments object.  It is a builtin array-like object  but doesn't have all the properties and methods an Array object has.
- The arguments object does have a length property so you can access arguments by index number
- you can use it when you want to access the arguments in a function call but don't know how many there might be.

**example:**

```
function x(a, b, n...) { // can have any number of args.
	// iterate through the arguments...
	for (var i = 0; i < arguments.length; i++) {

		console.log(arguments[i]);
		// logs each argument
	}
}
```

### recursion
Recursion in a function means that within the function, the function calls itself.
-typically have a base case that says when to stop recursion and a recurring case where the function is called.

**Example:**

```
function runUntilYouStop(num, stopper) {
    if (num <= stopper) {
        // base case is num > stopper
        num = num * num;
        console.log(num);
        runUntilYouStop(num, stopper);
        // recurring case
    } else {
        return num;
    }
}

runUntilYouStop(3, 1000000);
```

### prototype
-a prototype is an object from which other objects inherit properties.
- every object has a prototype by default
- nearly all objects are instances of Object (Object.prototype)
- every prototype also has a prototype except the object at the very top of the prototype chain.

- Used for...
If you want to create a whole bunch of objects that share a bunch of properties and methods, you can add them to the prototype of that object.  Then, when you make a new object of that type, all the properties and methods of the prototype get inherited in the new object.

**Example:**

```
var cat = {
    name: 'name',
    fur: true,
    color: 'orange',
    legs: 4,
    tail: true
};

var snowball = Object.create(cat);
snowball.name = 'Snowball';

console.log(snowball.legs); // 4 - snowball inherited the legs: 4 property and value
```

### constructors
-The constructor function makes it possible to quickly create objects that derive from a prototype.
- any variable created with the word `new` in front of it will be treated as a constructor
- an object created with `new` is said to be an *instance of* its constructor

**Example of a constructor function:**

```
function Cat(name, legs, fur) {
    this.name = name;
    this.legs = legs; // number of legs
    this.fur = fur; // true or false
}

var snowball = new Cat('Snowball', 4, true);
console.log(snowball);
// -> Cat { name: 'Snowball', legs: 4, fur: true }
```


2. Fork and clone this repo.  When you need to commit use the following commands.

	* git status
	* git add --all
	* git status
	* git commit -m "your commit message"
	* git push origin master

3. Install dependencies using `npm install`.  Run tests using `npm test`.

4. Make the tests pass!


#### Congratulations on finishing Homework #4!
Apply to our full-time or part-time immersive program to learn cutting edge technologies that are used by top technology companies around the world.

Our part-time and full-time courses are 13 intense weeks of focused study on the most relevant technologies.

Class sizes are small to ensure that each student gets individual attention from our world class instructors to help them succeed.  We also provide career support both during and after the course to help you succeed.  We are committed to your success.

For more information visit: https://www.lambdaschool.com

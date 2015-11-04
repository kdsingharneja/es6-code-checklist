# ECMAScript 2015 Code Patterns

A code pattern/review checklist for ES6 features. If you are developing with ES6, then keep these in mind as chances are we will stick to old habits. Feel free to refer to these for your reference in development and code reviews.

## Prefer let

Block scoping is available now, hence use **let** whenever possible for block scope, such as loops.

```
var x = 0;

for (**let** i = 0; i < 10; i++) {
    x += 10;
}

try {
	console.log(i);
} catch(e) {
	console.log(
		'i does not exist here!'
	);
}
```
## Prefer const

Instead of 

```
var PI = 3.14159265359
```
on the top level scope, do...

```
const PI = 3.14159265359
```
on application wide scope. These are immutable!!

## Prefer class features

If you must go classical class approach, then use **class**. This is going more Java way of doing things but you will still able to write object oriented prototype patterns with a classical classes approach, the class syntax has support for inheritance, super calls, instance and static properties and constructors.

```
class Prius extends Car { //**extends** available now
  constructor(speed) { // **constructor** available now
    super(); //**super** available now
    this.speed = speed;
  }

  get speed() {
    return 40;
  }

  drive() {
    super.drive();
  }

  static create() {  //**singleton** baby!
    return new Prius();
  }
}
```






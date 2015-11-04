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
class Prius extends Car { //'extends' available now
  constructor(speed) { //'constructor' available now
    super(); //'super' available now
    this.speed = speed;
  }

  get speed() {
    return 40;
  }

  drive() {
    super.drive();
  }

  static create() {  //'factory' baby!
    return new Prius();
  }
}
```

## Prefer default param values and reduce code

Instead of 

```
function f(x, y) {
  y = y || 100;
  return x + y;
}
```
do

```
function f(x, y = 100) {
  return x + y;
}
```

## Simplify assignments

In order to make something like

```
var node = {
  position: [0, 0],
  title: 'Default',
  color: 'red',
  width: 10
};
```
Avoid this...

```
var x = node.position[0];
var y = node.position[1];
var title = node.title;
var color = node.color;
var width = node.width;
```

..and do this...

```
var [x, y] = node.position;
var { title, color, width } = node;
```

## Use for-of

This should help in misusing for-in as well as reduce code

```
let myArray = [3, 5, 7];

for (let i of myArray) {
   console.log(i); // logs "3", "5", "7"
}
```


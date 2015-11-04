# ECMAScript 2015 Code Patterns

A code pattern/review checklist for ES6 features. Feel free to refer to these for your reference in development and code reviews.

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




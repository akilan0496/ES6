### Arrows

Arrows are a function shorthand using the => syntax.


* First, they are less verbose than traditional function expressions:

//ES6
```javascript
const arr = [1, 2, 3];
const squares = arr.map(x => x * x);
```
// ES5:
```javascript
const squares = arr.map(function (x) { return x * x });
```

* Second, their this is picked up from surroundings (lexical). Therefore, you don’t need bind() or that = this, anymore.

//ES6
```javascript
function UiComponent() {
    const button = document.getElementById('myButton');
    button.addEventListener('click', () => {
        this.handleClick(); // lexical `this`
    });
}
```
//ES5
```javascript
function UiComponent() {
	var _self = this;
    const button = document.getElementById('myButton');
    button.addEventListener('click', () => {
        _self.handleClick(); // lexical `this`
    });
}
```

Specifying parameters:

    () => { ... } // no parameter
     x => { ... } // one parameter, an identifier
	(x, y) => { ... } // several parameters

Specifying a body:

	x => { return x * x }  // block
	x => x * x  // expression, equivalent to previous line

The following variables are all lexical inside arrow functions:

* arguments
* super
* this
* new.target


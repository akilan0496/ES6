### Constants: 

Support for constants (also known as <b>"immutable variables"</b>), i.e., variables which cannot be re-assigned new content. Notice: this only makes the variable itself immutable, <b>not its assigned content</b> (for instance, in case the content is an object, this means the object itself can still be altered).
	
And here's some ES6 code! :+1:

```javascript
const PI = 3.141593
PI > 3.0
```

And here's some ES5 code! :+1:
```javascript
//  only in ES5 through the help of object properties
//  and only in global context and not in a block scope
Object.defineProperty(typeof global === "object" ? global : window, "PI", {
    value:        3.141593,
    enumerable:   true,
    writable:     false,
    configurable: false
})
PI > 3.0;
```

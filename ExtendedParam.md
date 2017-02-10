### Extended Parameter Handling

 * Default Parameter Values

	Simple and intuitive default values for function parameters.

	//ES6
    ```javascript
    function f (x, y = 7, z = 42) {
        return x + y + z;
    }
    console.log(f(1) === 50); // true
    ```
    
    //ES5
    ```javascript
    function f (x, y, z) {
		if (y === undefined)
            y = 7;
        if (z === undefined)
            z = 42;
        return x + y + z;
    };
    console.log(f(1) === 50); // true
    ```
 * Rest Parameter

	Aggregation of remaining arguments into single parameter of variadic functions.
    
    //ES6
    ```javascript
    function f (x, y, ...a) {
        console.log(a); //["hello", true, 7]
        return x * y * a[2]; //14
    };
    f(1, 2, "hello", true, 7);
    
    ```
    
    //ES5
    ```javascript
    function f (x, y) {
        var a = Array.prototype.slice.call(arguments, 2);
        console.log(a); //["hello", true, 7]
        return x * y * a[2]; //14
    };
    f(1, 2, "hello", true, 7);
    
    ```
    
 * Spread Operator

	Spreading of elements of an iterable collection (like an array or even a string) into both literal elements and individual function parameters.
    
    //ES6
    ```javascript
    var params = [ "hello", true, 7 ]
    var other = [ 1, 2, ...params ] // [ 1, 2, "hello", true, 7 ]

    var str = "foo"
    var chars = [ ...str ] // [ "f", "o", "o" ]
    
    ```
    
    //ES5
    ```javascript
    var params = [ "hello", true, 7 ];
    var other = [ 1, 2 ].concat(params); // [ 1, 2, "hello", true, 7 ]

    var str = "foo";
    var chars = str.split(""); // [ "f", "o", "o" ]
    
    ```
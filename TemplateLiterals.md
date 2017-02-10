### Template Literals



 * String Interpolation
 
   Intuitive expression interpolation for single-line and multi-line strings. 
   
   (Notice: don't be confused, Template Literals were originally named "Template Strings" in the drafts of the ECMAScript 6 language specification)
   
   //ES6
	```javascript
	var customer = { name: "Foo" }
    var card = { amount: 7, product: "Bar", unitprice: 42 }
    var message = `Hello ${customer.name}, want to buy ${card.amount} ${card.product} for a total of ${card.amount * card.unitprice} bucks?`
	```
	//ES6
	```javascript
	var customer = { name: "Foo" };
    var card = { amount: 7, product: "Bar", unitprice: 42 };
    var message = "Hello " + customer.name + ", want to buy " + card.amount + card.product + " for a total of " + (card.amount * card.unitprice) + " bucks?";
	```
 * Custom Interpolation
 
	Flexible expression interpolation for arbitrary methods.
    
    //ES6
    ```javascript
    get`http://example.com/foo?bar=${bar + baz}&quux=${quux}`
    ```
    //ES5
    ```javascript
    get([ "http://example.com/foo?bar=", "&quux=", "" ],bar + baz, quux);
    ```
 * Raw String Access

	Access the raw template string content (backslashes are not interpreted).
    
    ```javascript
    function quux (strings, ...values) {
        strings[0] === "foo\n"
        strings[1] === "bar"
        strings.raw[0] === "foo\\n"
        strings.raw[1] === "bar"
        values[0] === 42
    }
    quux `foo\n${ 42 }bar`

    String.raw `foo\n${ 42 }bar` === "foo\\n42bar"
    ```


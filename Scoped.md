### Scoping


 * Block-Scoped Variables
 ```javascript
 {
   {
     let x = 5;
     {
       let x = 6;
       console.log(x); // prints 6
     }
     console.log(x); // prints 5
   }
}
```

 * Block-Scoped Functions

 ```javascript
 {
   {
     function foo() {return 5};
     {
       function foo() {return 6};
       console.log(foo() === 6); // true
     }
     console.log(foo() === 5); // true
   }
}
```
 * Let + Const
```javascript
  function f() {
    {
      let x;
      {
        // okay, block scoped name
        const x = "block";
        // error, const
        x = "foo";
      }
      // error, already declared in block
      let x = "inner";
    }
  }
  ```

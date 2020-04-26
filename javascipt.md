## Function
- _  is a special kind of object in JavaScript, it's a first class data type. That means we can add properties to it. [permadi.com](http://www.permadi.com/tutorial/jsFunc/index.html)

## Function Types

```
// function declaration
functionTwo(); // Outputs: "Hello!"
function functionTwo() {}

// function expression
functionOne(); // TypeError: functionOne is not a function
var functionOne = function() {};
```

- **function declaration** is defined as soon as its surrounding function or script is executed (due to hoisting). [stackoverflow](https://stackoverflow.com/a/336868)
- **function expression** is defined when that line is reached. it may make more sense when you consider that a function is an object, and we're just assigning a name to the object [permadi.com](http://www.permadi.com/tutorial/jsFunc/index.html)
  - `var fn = function test(){}` *named* function expression. Useful if they need to reference themselves (e.g. for recursive calls)
  - `var fn = function (){}` *anonymous* function expression. In ES2015 the function is assigned a name if possible by inferring it from context
  - `() => {}` *arrow* function expression. Available since ES2015, `this` is lexically bound, not determined when they're called [stackoverflow](https://stackoverflow.com/a/22173438)
- **function constructor** - tdb [mozilla](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

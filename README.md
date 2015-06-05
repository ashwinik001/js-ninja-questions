# js-ninja-questions

### Questions and Solutions for JS Ninjas

#### Please feel free to add or update any of the following
#### Your suggestions for improvement are more than welcome at kumarashwini@outlook.com












### Questions Here *(Solutions are below)*

**Question 1.** Make the following Javascript code work for any number of arguments?

```javascript
console.info(''+multiply(5, 6));    // 30
console.info(''+multiply(5)(6));    // 30
console.info(''+multiply(5, 2, 3)); // 30
console.info(''+multiply(5)(2)(3)); // 30
```

**Question 2.**  What will be the following three outputs

```javascript
var z={},
    y={'0':'nice'},
    x={'1':'nicer'};
z[y] = 0;
z[x] = 1;
console.log(z[y]);
console.log(z[x]);
console.log(z[y] === z[x]);
```

**Question 3.**  More Questions to be added... :wink:












### Now Solutions

**Solution 1.**

```javascript
var multiply = function() {
  var currentResult = eval(Array.prototype.join.call(arguments, '*'));
  multiply.lastResult = (multiply.lastResult ? (multiply.lastResult*currentResult) : currentResult);
  return multiply;
};
multiply.toString = function() {
  var temp = multiply.lastResult;
  multiply.lastResult = null;
  return temp;
};
//Test Cases
console.info(''+multiply(5, 6));    // 30
console.info(''+multiply(5)(6));    // 30
console.info(''+multiply(5, 2, 3)); // 30
console.info(''+multiply(5)(2)(3)); // 30
```

**Solution 2.**

```javascript
var z={},
    y={'0':'nice'},
    x={'1':'nicer'};
z[y] = 0;
z[x] = 1;
console.log(z[y]);          \\1
console.log(z[x]);          \\1
console.log(z[y] === z[x]); \\true
```

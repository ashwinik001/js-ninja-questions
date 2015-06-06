# js-ninja-questions

### Questions and Solutions for JS Ninjas

##### Please feel free to add or update any of the following
##### Your suggestions for improvement are more than welcome at kumarashwini@outlook.com












### Questions Here *(Solutions are below)*

**Question 1.** Make the following Javascript code work for any number of arguments and combinations

```javascript
console.info(''+multiply(5, 6));    // 30
console.info(''+multiply(5)(6));    // 30
console.info(''+multiply(5, 2)(3)); // 30
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

**Question 3.**  How about the equality checks between the objects with the same content

```javascript
var a = {'key': 'value'};
var b = {'key': 'value'};
console.info(a == b);
console.info(a === b);
```

**Question 4.** Let's implement a getUniqueId with *auto incrementing* in JS

```javascript
getUniqueId(); // 1
getUniqueId(); // 2
getUniqueId(); // 3
```

**Question 5.**  More Questions to be added... :wink:












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
console.info(''+multiply(5, 2)(3)); // 30
console.info(''+multiply(5)(2)(3)); // 30
```

**Solution 2.**

```javascript
var z={},
    y={'0':'nice'},
    x={'1':'nicer'};
z[y] = 0;
z[x] = 1;
console.log(z[y]);          //1
console.log(z[x]);          //1
console.log(z[y] === z[x]); //true
```

**Solution 3.**

```javascript
var a = {'key': 'value'};
var b = {'key': 'value'};
console.info(a == b);   // false
console.info(a === b);  // false 
```

**Solution 4.**

Option 1 - Let's thrill with overriding the function itself being inside the function :skull:

```javascript
var getUniqueId = function() {
    var id = 0;
    getUniqueId = function() {
        return ++id;
    };
    return ++id;
};
```

Option 2 - Using IIFE

```javascript
var getUniqueId = (function() {
    var id = 0;
    return function() {
        return ++id;
    };
})();
```

Let's Test with either of the two

```javascript
getUniqueId(); // 1
getUniqueId(); // 2
getUniqueId(); // 3
```

## Best JS quotes and code extractions
Just random copy&pastes from the web ...

* #1 arrays and objects are passed by reference ﬁhttps://medium.com/javascript-scene/the-single-biggest-mistake-programmers-make-every-day-62366b432308

> In JavaScript, arrays and objects are passed by reference, so if you mutate array or object parameters, it doesn’t just affect the variable inside the function. It also affects any other function that uses a reference to the same variable.

* #2 iterable protocol https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols

> The iterable protocol allows JavaScript objects to define or customize their iteration behavior, such as what values are looped over in a for..of construct. Some built-in types are built-in iterables with a default iteration behavior, such as Array or Map, while other types (such as Object) are not.

* #3 http://chimera.labs.oreilly.com/books/1234000000262/ch02.html#side-effects

> !!! If your function operates on outside variables, return a copy instead of the original.

* #4 function expression
```
var bar = function () {
    return arguments.callee;
};

bar(); //=> [Function] (Note: It's anonymous.)
```
> The bar() example assigns a function body to the variable, bar. This implementation is called a function expression.

* #5 object literal
```
var myObject = {
    sProp: 'some string value',
    numProp: 2,
    bProp: false
};
```
> An object literal is a comma-separated list of name-value pairs wrapped in curly braces. Object literals encapsulate data, enclosing it in a tidy package. This minimizes the use of global variables which can cause problems when combining code.

* #6 Named function expressions
```
test('Named function expressions.', function () {
  var a = function x () {
    ok(x, 'x() is usable inside the function.');
  };

  a();

  try {
    x(); // Error
  } catch (e) {
    ok(true, 'x() is undefined outside the function.');
  }
});
```

* #7 Lambda
     
> A lambda is a function that is used as data. As such, it can be used the same way any other expression can: as a parameter for another function, the return value of a function, or anywhere you might use a literal value.

```
var sum = function sum() {
  var result = 0;

  [5, 5, 5].forEach(function addTo(number) { result += number; });

  return result;
};

test('Lambdas.', function () {
  equal(sum(), 15,
    'result should be 15.');
});
```
The .addTo() function passed into .forEach() is a lambda. 

> .addTo() has access to the result variable from the containing function scope's closure
> .forEach() method is one of several **functional enumerators** added to ES5

- [ ] Lambdas are frequently confused with anonymous functions, closures, first-class functions, and higher order functions. The concepts are all similar, but they mean different things.



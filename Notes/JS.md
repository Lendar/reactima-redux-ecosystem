## Best JS quotes and code extractions
Just random copy&pastes from the web ... 

* 1 **arrays and objects are passed by reference** https://medium.com/javascript-scene/the-single-biggest-mistake-programmers-make-every-day-62366b432308

> In JavaScript, arrays and objects are passed by reference, so if you mutate array or object parameters, it doesn’t just affect the variable inside the function. It also affects any other function that uses a reference to the same variable.

* 2 **iterable protocol** https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols

> The iterable protocol allows JavaScript objects to define or customize their iteration behavior, such as what values are looped over in a for..of construct. Some built-in types are built-in iterables with a default iteration behavior, such as Array or Map, while other types (such as Object) are not.

## Chapter 2. Functions

[Programming JavaScript Applications](http://chimera.labs.oreilly.com/books/1234000000262/ch02.html#side-effects) uses  several (QUnit](https://qunitjs.com/) functions: module(), test(), ok(), equal()

* 3 If your function operates on outside variables, return a copy instead of the original.

* 4 **function expression**
```javascript
var bar = function () {
    return arguments.callee;
};

bar(); //=> [Function] (Note: It's anonymous.)
```
> The bar() example assigns a function body to the variable, bar. This implementation is called a function expression.

* 5 **object literal**

```javascript
var myObject = {
    sProp: 'some string value',
    numProp: 2,
    bProp: false
};
```
> An object literal is a comma-separated list of name-value pairs wrapped in curly braces. Object literals encapsulate data, enclosing it in a tidy package. This minimizes the use of global variables which can cause problems when combining code.

* 6 **named function expressions**

```javascript
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

* 7 **lambda**
     
> A lambda is a function that is used as data. As such, it can be used the same way any other expression can: as a parameter for another function, the return value of a function, or anywhere you might use a literal value.

```javascript
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

```
.addTo() has access to the result variable from the containing function scope's closure 
.forEach() method is one of several **functional enumerators** added to ES5
```

* 8 **Closure vs Lambda vs First-class vs Higher Order** functions

  * Lambdas are frequently confused with anonymous functions, closures **14**, first-class functions, and higher order functions. The concepts are all similar, but they mean different things.
  * A closure is created when a function references data that is contained outside the function scope. A lambda is a function that is used as a value (assigned to a variable or passed between functions)
  * Higher-order functions are functions that consume or return functions as data. Lambdas get passed to and/or returned from higher order functions, and a function might be both a lambda and a higher order function, but not all higher order functions are lambdas.
  * If a function is used as an argument or return value, it's a lambda.

* 9 **Method Context**
[JavaScript 4 Function Invocations](http://www.w3schools.com/js/js_function_invocation.asp)

```javascript
function highPass(number, cutoff) {
    cutoff = cutoff || this.cutoff;
    return (number >= cutoff);
}

var filter1 = {
    highPass: highPass,
    cutoff: 5
  },
  filter2 = {
    // No highPass here!
    cutoff: 3
  };

test('Invoking a method.', function () {
  var result1 = filter1.highPass(3),
    result2 = highPass.call(filter2, 3),
    result3 = filter1.highPass(6);

  equal(result1, false,
    '3 >= filter1.cutoff should be false.');

  equal(result2, true,
    '3 >= filter2.cutoff should be true.');

  equal(result3, true,
    '6 >= filter1.cutoff should be true.');
});
```

  * When you invoke a method with dot notation, you have access to the object's properties using this. The number parameter is compared to filter1.cutoff. The method returns false because 3 is less than the value stored in this.cutoff, which refers to filter1.cutoff. Remember, this refers to the object that the method is called on.

  * In the second example, the call method (inherited from Function.prototype) delegates to the method on filter2 instead. Because filter2.cutoff is 3 instead of 5, the same test passes this time.

  * To clarify, the [.call()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call) method shared by all functions allows you to call any method or function on any object. In other words, it sets this inside the method to refer to the object of your choosing. The signature is:
  
```
someMethod.call(context, argument1, argument2, ...);
```

Here, context is the object you want this to refer to. If you need to pass an array of arguments, use .apply() instead:

```
someMethod.apply(context, someArray);
```

* 10 **Function.prototype.bind()**
[.call()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call) [.apply()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply) [.bind()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)  

.call() and .apply() drawback: they impermanently bind the context to the target method. You have to remember to use them every time you invoke the method, and you have to have access to the context object in scope. That's not always easy, particularly in event handlers.The .bind() method is used to permanently set the value of this inside the target function to the passed in context object. 

```
var lightbulb = {
    toggle: function toggle() {
      this.isOn = !this.isOn;
      return this.isOn;
    },
    isOn: false
  },
  toggle = lightbulb.toggle.bind(lightbulb);
  lightswitch = document.getElementById('lightswitch');

lightswitch = document.getElementById('lightswitch');
lightswitch.addEventListener('click',
  lightbulb.toggle, false);
```  

* 11 **()()**
```
function hi(){
    return function(){return "hello there";};
}

var returnedFunc = hi();  // so returnedFunc equals function(){return "hello there";};
var msg = hi()();         // so msg now has a value of "hello there"
```


* 12 **Function Scope**
  * Variable scope is the section of code in which the identifier refers to the expected value. 
  * Outside a variable's scope, the variable is undefined or replaced by another variable with the same name.  
  * The var keyword is not block scoped. var uses function scope instead. Block scope is available using the let keyword in ES6. 
  * !!! The desire to use block scope can be a good code smell that indicates that it may be time to break a function into smaller pieces in order to encourage readability, organization, and code reuse. It's a good idea to keep functions small.


* 13 **Hoisting** aka always declare all variables at the beginning of every scope.
  * Hoisting is the word most commonly used to describe the illusion that all variable declarations are "hoisted" to the top of the containing function. Technically, that's not exactly how it happens, but the effect is the same.
  * JavaScript builds its execution environment in two passes. 
    * The declaration pass sets up the runtime environment, where it scans for all variable and function declarations and creates the identifiers. The second pass is the execution pass. 
    * After the first pass, all declared functions are available, but variables are still undefined. 
    
```
var x = 1;

(function () {
  console.log(x);
  var x = 2;
}());
```

If you guessed that the value of x at the console.log() statement is 1, you're not alone. This is a common source of bugs in JavaScript. In the first pass, the function declarations occur, and x is undefined in both the inner and outer scope. When it gets to the console.log() statement in the execution pass, the inner scoped x has been declared, but is still undefined, because it hasn't hit the initialization in the next statement yet. In effect, this is how JavaScript interprets the code:

```
var x = 1;

(function () {
  var x; // Declaration is hoisted and x is undefined.
  console.log(x);
  x = 2; // Initialization is still down here.
}());
```

Functions behave a little differently. Both the identifier number and the function body are hoisted, whereas the value 2 was not hoisted along with x:

```
test('Function declaration hoisting', function () {
  function number() {
    return 1;
  }

  (function () {
    equal(number(), 2, 'Inner scope wins.');

    function number() {
      return 2;
    }
  }());

  equal(number(), 1, 'Outer scope still works.');
});
```

This code is equivalent to:

```
test('Function declaration hoisted.', function () {
  function number() {
    return 1;
  }

  (function () {
    function number() {
      return 2;
    }

    equal(number(), 2, 'Inner scope wins.');
  }());

  equal(number(), 1, 'Outer scope still works.');
});
```

Function expressions do not share this behavior, because they do not declare a function. Instead, they declare a variable and are subject to the same variable-hoisting behavior:

```
test('Function expression hoisting', function () {
  function number() {
    return 1;
  }

  (function () {
    try {
      number();
    } catch (e) {
      ok(true, 'number() is undefined.');
    }

    var number = function number() {
      return 2;
    }

    equal(number(), 2, 'number() is defined now.');
  }());

  equal(number(), 1, 'Outer scope still works.');
});
```

In the function expression example, the number variable is hoisted, but the function body is not hoisted, because it is a named function expression, not a function declaration. The value of number is not defined until runtime. This code is equivalent to:

```
test('Function Expression Hoisted', function () {
  function number() {
    return 1;
  }

  (function () {
    var number; // Declaration initialized to undefined.

    try {
      number();
    } catch (e) {
      ok(true, 'number() is undefined.');
    }

    number = function number() {
      return 2;
    }

    equal(number(), 2, 'number() is defined now.');
  }());

  equal(number(), 1, 'Outer scope still works.');
});
```


* 14 **Closures** - critical to successful application development ;)

In a nutshell, a closure stores function state, even after the function has returned. To create a closure, simply define a function inside another function and expose it. To expose a function, return it or pass it to another function. The inner function will have access to the variables declared in the outer function. This technique is commonly used to give objects data privacy.

Because the closure variables in the outer function are only in scope within the containing function, you can't get at the data except through its privileged methods. In other languages, a privileged method is an exposed method that has access to private data. !!! In JavaScript, **any exposed method defined within the closure scope is privileged**. For example:

```
var o = function o () {
  var data = 1,
    get;

  get = function get() {
    return data;
  };

  return {
    get: get
  };
};

test('Closure for object privacy.', function () {
  var obj = o(); // Get an object with the .get() method.

  try {
    ok(data, 'This throws an error.');
  } catch (e) {
    ok(true,'The data var is only available'
      + ' to privileged methods.');
  }

  equal(
    obj.get(), 1,
    '.get() should have access to the closure.'
  );
});
```

In this example, o is an object factory that defines the private variable data and a privileged method, .get(), that has access to it. The factory exposes .get() in the object literal that it returns.

In the test, the return value from o is assigned to the obj variable. In the try block, the attempt to access the private data var throws an error because it is undeclared outside the closure scope.

In addition to the data privacy benefits, closures are an essential ingredient in languages that support first-class functions, because they give you access to outer scope variables from inside your lambdas.

Closures are commonly used to feed data to event handlers or callbacks, which might get triggered long after the containing function has finished. For example:

```
(function () {
  var arr = [],
    count = 1,
    delay = 20,
    timer,
    complete;

  timer = function timer() {
    setTimeout(function inner() {
      arr.push(count);

      if (count < 3) {
        count += 1;
        timer();
      } else {
        complete();
      }
    }, delay);
  };

  asyncTest('Closure with setTimeout.', function () {
    complete = function complete() {
      equal(
        arr.join(','), '1,2,3',
        'arr should be [1,2,3]'
      );
      start();
    };

    timer();

    equal(
      arr.length, 0,
      'array should be empty until the first timout.'
    );
  });
}());
```
In this example, the inner() lambda has access to arr, complete(), and count from the containing function. Its job is to add the current count to the array each time it's called. If the array isn't full yet, it calls the timer() function to set a new timeout so it will be invoked again after the delay has expired.

This is an example of asynchronous recursion, and the pattern is sometimes used to retry Ajax requests when they fail. There is usually a retry limit and a delay so that the server doesn't get hammered with endless retries from millions of users.

The asyncTest() function is provided by QUnit as a shortcut for running asynchronous tests. Normally, you need to call stop() at the top of your test to tell QUnit that you're expecting assertions to fire asynchronously. The stop() function suspends the completion of the test until start() gets called.

When the test runs, the complete() function gets defined. It will later be called from inner() after all of the timeouts have expired. The complete function defines an equal() assertion to verify the contents of arr.

As you can see, the final equal() assertion in the program listing is actually the first one that gets run. That's because the first timeout has not had time to expire before the JavaScript engine gets to that line in the code. At that point, any attempt to read arr or count will return the initial values. The values don't get modified until the first timeout expires and inner() has had a chance to run.

Each time inner() gets called, count is incremented and pushed onto the array, arr. Since count and arr were defined inside the closure, it's possible to access them from other functions in the same scope, which is why we can test them in the asyncTest() call.

* 15 **Method Design**
  * Several techniques exist in JavaScript to design method APIs. 
  * JavaScript supports 
    * named parameter lists, 
    * function polymorphism, 
    * method chaining, and 
    * lambda expressions. 

* 15 **Named Parameters**
Garbage was here ... See ES6 destructing, spread, etc

* 16 **Function Polymorphism**
  * Polymorphism means that something behaves differently based on context
  * Polymorphic functions behave differently based on the parameters you pass into them. In JavaScript, those parameters are stored in the array-like arguments object, but it’s missing useful array methods.
  * Array.prototype.[slice()](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) is an easy way to shallow copy some or all of an array (or an array-like object). You can borrow the .slice() method from the Array prototype using a technique called **method delegation**. You delegate the .slice() call to the Array.prototype object.
  
```
var args = Array.prototype.slice.call(arguments, 0);
```

Slice starts at index 0 and returns everything from that index on as a new array. That syntax is a little long winded, though. It's easier and faster to write:
```
var args = [].slice.call(arguments, 0);
```
The square bracket notation creates a new empty array to delegate the slice call to. That sounds like it might be slow, but creating an empty array is actually a very fast operation. I ran an A/B performance test with millions of operations and didn't see a blip in the memory use or any statistically significant difference in operation speed.

You could use this technique to create a function that sorts parameters:
```
function sort() {
  var args = [].slice.call(arguments, 0);
  return args.sort();
}

test('Sort', function () {
  var result = sort('b', 'a', 'c');   
  ok(result, ['a', 'b', 'c'], 'Sort works!');
});
```

Because arguments is not a real array, it doesn't have the .sort() method. However, since a real array is returned from the .slice() call, you have access to all of the array methods on the args array. The .sort() method returns a sorted version of the array.

Polymorphic functions frequently need to examine the first argument in order to decide how to respond. Now that args is a real array, you can use the .shift() method to get the first argument:
```
var first = args.shift();
```
Now you can branch if a string is passed as the first parameter:
```
function morph(options) {
  var args = [].slice.call(arguments, 0),
    animals = 'turtles'; // Set a default

  if (typeof options === 'string') {
    animals = options;
    args.shift();
  }

  return('The pet store has ' + args + ' ' + animals
    + '.');
}

test('Polymorphic branching.', function () {
  var test1 = morph('cats', 3),
    test2 = morph('dogs', 4),
    test3 = morph(2);

  equal(test1, 'The pet store has 3 cats.', '3 Cats.');
  equal(test2, 'The pet store has 4 dogs.', '4 Dogs.');
  equal(test3, 'The pet store has 2 turtles.',
    'The pet store has 2 turtles.');
});
```
* 16 **Method dispatch**
  * Method dispatch is the mechanism that determines what to do when an object receives a message. JavaScript does this by checking to see if the method exists on the object. If it doesn't, the JavaScript engine checks the prototype object. If the method isn't there, it checks the prototype's prototype, and so on. When it finds a matching method, it calls the method and passes the parameters in. This is also known as behavior delegation in delegation-based prototypal languages like JavaScript.

  * Dynamic dispatch enables polymorphism by selecting the appropriate method to run based on the parameters that get passed into the method at runtime. Some languages have special syntax to support dynamic dispatch. In JavaScript, you can check the parameters from within the called method and call another method in response:

```
var methods = {
    init: function (args) {
      return 'initializing...';
    },
    hello: function (args) {
      return 'Hello, ' + args;
    },
    goodbye: function (args) {
      return 'Goodbye, cruel ' + args;
    }
  },
  greet = function greet(options) {
    var args = [].slice.call(arguments, 0),
      initialized = false,
      action = 'init'; // init will run by default

    if (typeof options === 'string' &&
        typeof methods[options] === 'function') {

      action = options;
      args.shift();
    }

    return methods[action](args);
  };

test('Dynamic dispatch', function () {
  var test1 = greet(),
    test2 = greet('hello', 'world!'),
    test3 = greet('goodbye', 'world!');
  
  equal(test2, 'Hello, world!',
    'Dispatched to hello method.');

  equal(test3, 'Goodbye, cruel world!',
    'Dispatched to goodbye method.');
});
```
This manual style of dynamic dispatch is a common technique in jQuery plug-ins in order to enable developers to add many methods to a plug-in without adding them all to the jQuery prototype (jQuery.fn). Using this technique, you can claim a single name on the jQuery prototype and add as many methods as you like to it. Users then select the method they want to invoke using:

```
$(selection).yourPlugin('methodName', params);
```

* 17 **Generics and Collection Polymorphism**

Generic programming is a style that attempts to express algorithms and data structures in a way that is type agnostic. The idea is that most algorithms can be employed across a variety of different types. Generic programming typically starts with one or more type-specific implementations, which then get lifted (abstracted) to create a more generic version that will work with a new set of types.

Generics do not require conditional logic branching to implement an algorithm differently based on the type of data passed in. Rather, the datatypes passed in must support the required features that the algorithm needs in order to work. Those features are called requirements, which in turn get collected into sets called concepts.

Generics employ parametric polymorphism, which uses a single branch of logic applied to generic type parameters. In contrast, ad-hoc polymorphism relies on conditional branching to handle the treatment of different parameter types (either built into the language with features like dynamic dispatch or introduced at program design time).

Generic programming is particularly relevant to functional programming because functional programming works best when a simple function vocabulary can express a wide range of functionality, regardless of type.

In most languages, generic programming is concerned with making algorithms work for different types of lists. In JavaScript, any collection (array or object) can contain any type (or mix of types), and most programmers rely on duck typing to accomplish similar goals. (If it walks like a duck and quacks like a duck, treat it like a duck. In other words, if an object has the features you need, assume it's the right kind of object and use it.) Many of the built-in object methods are generics, meaning that they can operate on multiple types of objects.

JavaScript supports two types of collections: objects and arrays. The principle difference between an object and an array is that one is keyed with names and the other sequentially with numbers. Objects don't guarantee any particular order; arrays do. Other than that, both behave pretty much the same. It often makes sense to implement functions that work regardless of which type of collection gets passed in.

Many of the functions you might apply to an array would also work for an object and vice versa. For example, say you want to select a random member from an object or array.

The easiest way to select a random element is to use a numbered index, so if the collection is an object, it could be converted to an array using ad-hoc polymorphism. The following function will do that:

```
var toArray = function toArray(obj) {
  var arr = [],
    prop;

  for (prop in obj) {
    if (obj.hasOwnProperty(prop)) {
      arr.push(prop);
    }
  }
  return arr;
};
```

The randomItem() function is easy now. First, you test the type of collection that gets passed in and convert it to an array if it's not one already, and then return a random item from the array using the built-in Math.random() method:

```
var randomItem = function randomItem(collection) {
  var arr = ({}.toString.call(collection) !== 
    '[object Array]')
      ? toArray(collection)
      : collection;
  return arr[Math.floor(arr.length * Math.random())];
};

test('randomItem()', function () {
  var obj = {
      a: 'a',
      b: 'b',
      c: 'c'
    },
    arr = ['a', 'b', 'c'];

  ok(obj.hasOwnProperty(randomItem(obj)),
    'randomItem works on Objects.');

  ok(obj.hasOwnProperty(randomItem(arr)),
    'randomItem works on Arrays.');
});
```

These tests check to see if the returned value exists in the test object.

Unlike true generics, this code relies on conditional branching internally to handle objects as a special case. Since arrays are already objects in JavaScript, a lot of what you might do with an object will work for arrays without any conversion. In other words, a lot of functions designed to act on JavaScript objects are truly generic in that they will also work for arrays without any specialized logic (assuming that the array has all of the required features).

Collection polymorphism is a very useful tool for code reuse and API consistency. Many library methods in both jQuery and Underscore work on both objects and arrays.

JavaScript 1.6 introduced a number of new built-in array and string generics. With 1.6 compatible JavaScript engines, you can use array methods such as .every() on strings:

```
var validString = 'abc',
  invalidString = 'abcd',

  validArray = ['a', 'b', 'c'],
  invalidArray = ['a', 'b', 'c', 'd'],

  isValid = function isValid(char) {
    return validString.indexOf(char) >= 0;
  };

test('Array String generics', function () {
  ok(![].every.call(invalidString, isValid),
    'invalidString is rejected.');

  ok([].every.call(validString, isValid),
    'validString passes.');

  ok(![].every.call(invalidArray, isValid),
    'invalidArray is rejected.');

  ok([].every.call(validArray, isValid),
    'validArray passes.');
});
```

You can also use string methods on numbers:

```
var num = 303;

test('String number generics', function () {
  var i = ''.indexOf.call(num, 0);

  ok(i === 1,
    'String methods work on numbers.');
});
```

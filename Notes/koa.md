### /tj/koa

### /tj/co
* [Co](https://github.com/tj/co) - Generator based control flow goodness for nodejs and the browser, using promises, letting you write non-blocking code in a nice-ish way.

`co@4.0.0` has been released, which now relies on promises.
  It is a stepping stone towards [ES7 async/await](https://github.com/lukehoban/ecmascript-asyncawait).
  The primary API change is how `co()` is invoked.
  Before, `co` returned a "thunk", which you then called with a callback and optional arguments.
  Now, `co()` returns a promise.

```js
co(function* () {
  var result = yield Promise.resolve(true);
  return result;
}).then(function (value) {
  console.log(value);
}, function (err) {
  console.error(err.stack);
});
```

  If you want to convert a `co`-generator-function into a regular function that returns a promise,
  you now use `co.wrap(fn*)`.

```js
var fn = co.wrap(function* (val) {
  return yield Promise.resolve(val);
});

fn(true).then(function (val) {

});
```
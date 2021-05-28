# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# js promise 的 es5 简单实现

```js
function TestPromise(fn) {
  const _this = this;
  let data;
  let thenFns = [];

  const resolve = function (value) {
    data = value;
    setTimeout(function () {
      _this.handleThen(thenFns.shift());
    }, 0);
  };

  this.then = function (thenFn) {
    thenFns.push(thenFn);
    return _this;
  };

  this.handleThen = function (thenFn) {
    data = thenFn.call(null, data);
    if (thenFns.length > 0) {
      setTimeout(function () {
        _this.handleThen(thenFns.shift());
      }, 0);
    }
  };

  fn.call(null, resolve);
}
```

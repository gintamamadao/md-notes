# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

```js
function throttle(fn, wait) {
  let last, timer;
  let interval = wait || 200;
  return function () {
    let th = this,
      args = arguments;
    let now = +new Date();
    if (now - last < interval) {
      clearTimeout(timer);
      timer = setTimeout(function () {
        last = now;
        fn.apply(th, args);
      }, interval);
    } else {
      last = now;
      fn.apply(th, args);
    }
  };
}
```

# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

- 通过闭包的方式储存传入参数
- 通过函数的 length 属性获得参数个数
- 当参数个数不够时直接返回方法
- 存储的参数个数等于原函数参数个数时执行原函数
- 如果使用 ES6 参数默认值，length 将不等于实际参数个数
- 参数由 arguments 获取，ES6 直接使用 rest 参数实现

```js
function curry(fn) {
  var length = fn.length; //获取原函数的参数个数
  var args = []; // args存储传入参数
  return function curryFn() {
    // 将arguments转换成数组
    var curryArgs = Array.prototype.slice.call(arguments);
    args = args.concat(curryArgs);
    if (args.length > length) {
      throw new Error("arguments length error");
    }
    // 存储的参数个数等于原函数参数个数时执行原函数
    if (args.length === length) {
      return fn.apply(null, args);
    }
    // 否则继续返回函数
    return curryFn;
  };
}
```

### ES6

```js
function curry(fn) {
  let length = fn.length;
  let args = [];
  return function curryFn(...curryArgs) {
    args = args.concat(curryArgs);
    if (args.length > length) {
      throw new Error("arguments length error");
    }
    if (args.length === length) {
      return fn(...args);
    }
    return curryFn;
  };
}
```

```js
function curry(fn) {
  const length = fn.length;
  const curryFn = (args) => (arg) => {
    const curryArgs = args.concat(arg);
    if (curryArgs.length === length) {
      return fn(...curryArgs);
    }
    return curryFn(curryArgs);
  };
  return curryFn([]);
}
```

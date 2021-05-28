# Parent Node

- [root](./root.md)
- [Promise then](./Promisethen.md)

# Child Node

# Detail

```js
Promise.resolve(1).then(2).then(Promise.resolve(3)).then(console.log);
```

- Promise.resolve 方法返回一个新的 Promise 对象
- then 方法接受的参数是函数，而如果传递的并非是一个函数，则跳过执行，而且值也不会更新，这就会导致前一个 Promise 的结果会穿透下面。

答案：1

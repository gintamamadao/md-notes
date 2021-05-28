# Parent Node

- [root](./root.md)
- [Promise api](./Promiseapi.md)

# Child Node

# Promise api resolve

`Promise.resolve(value)`

- 如果这个值是 thenable（即带有"then" 方法)）, 返回的 promise 会“跟随”这个 thenable 的对象, 采用它的最终状态,
- 否则返回的 Promise 对象状态为 fulfilled, 并且将该 value 传递给对应的 then 方法
- 不要在解析为自身的 thenable 上调用 Promise.resolve。这将导致无限递归，因为它试图展平无限嵌套的 promise。一个例子是将它与 Angular 中的异步管道一起使用。

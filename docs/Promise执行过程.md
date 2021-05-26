# Parent Node

- [/](./root.md)
- [../](./ECMAScriptPromise.md)

# Child Node

# Detail

- 新建 Promise 对象时, 要传入一个函数作为参数, 函数有两个形参 resolve 和 reject, 都是用于结束 Promise 的 pedding 状态的
- 新建时就会立即同步执行, 异步返回结果
- 每次 then 操作都是异步操作
- 无法中途取消进行中的 Promise

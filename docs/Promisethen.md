# Parent Node

- [root](./root.md)
- [ECMAScript Promise](./ECMAScriptPromise.md)

# Child Node

- [Promise then 传入非函数](./Promisethen传入非函数.md)

# Detail

- 多个 then 注册时按顺序执行
- 跟在 catch 的后面的 then 会继续执行，但拿到的数据是空的
- 跟在 finally 的后面的 then 会继续执行，但拿到的数据是空的
- finally 不可忽略，then 可以忽略
- then 可以在 finally 后执行

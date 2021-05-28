# Parent Node

- [root](./root.md)
- [ECMAScript Promise](./ECMAScriptPromise.md)

# Child Node

# Promise catch

- catch 可以捕获 then 中抛出的错误
- 跟在 catch 的后面的 then 会继续执行，但拿到的数据是空的
- 跟在 catch 的后面的 finally 会继续执行
- 跟在 catch 的后面的 catch, 如果前一个 catch 没有 throw 错误，则不会执行
- catch 后面有 catch， 那么 catch 抛出错误后，catch 和 catch 之间注册的 then 会被忽略，finally 不会
- catch 后面有 catch， 那么 catch 接受错误但没有抛出错误，那么后面的的 then 和 finally 按顺序会正常执行
- catch 后面没有有 catch， 那么 catch 接受错误但没有抛出错误，catch 之后面的 then 和 finally 按顺序会正常执行
- catch 后面没有有 catch， 那么 catch 抛出错误，catch 之后面的 then 不会执行，但 finally 按顺序会正常执行

# Parent Node

- [ROOT](./root.md)
- [qiankun 应用的隔离与通信](./qiankun应用的隔离与通信.md)

# Child Node

# qiankun js 的隔离

- qiankun 通过 import-html-entry，可以对 html 入口进行解析，并获得一个可以执行脚本的方法 execScripts。
- qiankun 引入该接口后，首先为该应用生成一个 window 的代理对象，然后将代理对象作为参数传入接口，
- 以保证应用内的 js 不会对全局 window 造成影响。
- 由于 IE11 不支持 proxy，所以 qiankun 通过快照策略来隔离 js，缺点是无法支持多实例场景。
- 核心代码就是由两个矩形框起来的部分，它把解析出的 scriptText（即脚本字符串）用 with(window){}包裹起来，
- 然后把 window.proxy 作为函数的第一个参数传进来，所以 with 语法内的 window 实际上是 window.proxy。

# Parent Node

- [ROOT](./root.md)
- [qiankun 应用的隔离与通信](./qiankun应用的隔离与通信.md)

# Child Node

# qiankun 应用之间的通信

- qiankun 官方提供了一个简要的方案，思路是基于一个全局的 globalState 对象。
- 这个对象由基座应用负责创建，内部包含一组用于通信的变量，以及两个分别用于修改变量值和监听变量变化的方法：setGlobalState 和 onGlobalStateChange。

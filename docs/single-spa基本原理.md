# Parent Node

- [ROOT](./root.md)
- [qiankun 应用的加载与切换](./qiankun应用的加载与切换.md)

# Child Node

- [single-spa 缺陷](./single-spa缺陷.md)

# single-spa 基本原理

- single-spa 是通过监听 hashChange 和 popState 这两个原生事件来检测路由变化的
- 它会根据路由的变化来加载对应的应用
- single-spa 采用的是协议入口，即只要实现了 single-spa 的入口协议规范，它就是可加载的应用。
- single-spa 的规范要求应用入口必须暴露出以下三个生命周期钩子函数，且必须返回 Promise，以保证 single-spa 可以注册回调函数：

  - bootstrap
  - mount
  - unmount

- 实际上 single-spa 并没有提供自己的解决方案，而是将它开放出来，由开发者提供

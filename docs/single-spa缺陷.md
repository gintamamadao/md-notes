# Parent Node

- [ROOT](./root.md)
- [single-spa 基本原理](./single-spa基本原理.md)

# Child Node

# single-spa 缺陷

- 首先我们必须手动实现应用加载逻辑，挨个罗列子应用需要加载的资源，这在大型项目里是十分困难的（特别是使用了文件名 hash 时）
- 另外它只能以 js 文件为入口，无法直接以 html 为入口，这使得嵌入子应用变得很困难，也正因此，single-spa 不能直接加载 jQuery 应用。
- single-spa 只是负责把应用加载到一个页面中，至于应用能否协同工作，是很难保证的

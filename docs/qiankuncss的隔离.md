# Parent Node

- [ROOT](./root.md)
- [qiankun 应用的隔离与通信](./qiankun应用的隔离与通信.md)

# Child Node

# qiankun css 的隔离

- qiankun 主要提供了两种样式隔离方案，一种是基于 shadowDom 的；
- 另一种则是实验性的，思路类似于 Vue 中的 scoped 属性，给每个子应用的根节点添加一个特殊属性，用作对所有 css 选择器的约束。
- 当启用 strictStyleIsolation 时，qiankun 将采用 shadowDom 的方式进行样式隔离，即为子应用的根节点创建一个 shadow root。
- 最终整个应用的所有 DOM 将形成一棵 shadow tree。
- 我们知道，shadowDom 的特点是，它内部所有节点的样式对树外面的节点无效，因此自然就实现了样式隔离。
- 但是这种方案是存在缺陷的。
- 因为某些 UI 框架可能会生成一些弹出框直接挂载到 document.body 下，此时由于脱离了 shadow tree，所以它的样式仍然会对全局造成污染。
- 此外 qiankun 也在探索类似于 Vue 中的 scoped 属性的样式隔离方案，可以通过 experimentalStyleIsolation 来开启。这种方案的策略是为子应用的根节点添加一个特定的随机属性

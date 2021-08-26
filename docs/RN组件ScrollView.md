# Parent Node

- [ROOT](./root.md)
- [RN 组件](./RN组件.md)

# Child Node

# RN 组件 ScrollView

- 一个封装了平台的 ScrollView（滚动视图）的组件，同时还集成了触摸锁定的“响应者”系统。
- 记住 ScrollView 必须有一个确定的高度才能正常工作
- ScrollView和FlatList应该如何选择？
- ScrollView 会简单粗暴地把所有子元素一次性全部渲染出来。
- FlatList会惰性渲染子元素，只在它们将要出现在屏幕中时开始渲染。
- 这种惰性渲染逻辑要复杂很多，因而 API 在使用上也更为繁琐。
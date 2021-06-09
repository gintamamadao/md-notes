# Parent Node

- [ROOT](./root.md)
- [qiankun 基本原理](./qiankun基本原理.md)

# Child Node

- [single-spa 基本原理](./single-spa基本原理.md)
- [import-html-entry](./import-html-entry.md)

# qiankun 应用的加载与切换

- qiankun 应用的加载与切换基于 single-spa 实现
- single-spa 提供的应用加载方案是开放式的。
- single-spa 的几个弊端，qiankun 进行了一次封装，给出了一个更完整的应用加载方案
- 该方案的主要思路是允许以 html 文件为应用入口，然后通过一个 html 解析器从文件中提取 js 和 css 依赖，并通过 fetch 下载依赖
- qiankun 的作者将其封装成了 npm 插件 import-html-entry

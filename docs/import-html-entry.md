# Parent Node

- [ROOT](./root.md)
- [qiankun 应用的加载与切换](./qiankun应用的加载与切换.md)

# Child Node

# import-html-entry

```js
const MicroApps = [
  {
    name: "app1",
    entry: "http://localhost:8080",
    container: "#app",
    activeRule: "/app1",
  },
];
```

- qiankun 会通过 import-html-entry 请求配置的 url，得到对应的 html 文件，
- 解析内部的所有 script 和 style 标签，依次下载和执行它们，这使得应用加载变得更易用。
- import-html-entry 暴露出的核心接口是 importHTML，用于加载 html 文件，它支持两个参数：

  - url，要加载的文件地址，一般是服务中 html 的地址
  - opts，配置参数

- url 不必多说。
- opts 如果是一个函数，则会替换默认的 fetch 作为下载文件的方法，此时其返回值应当是 Promise；
- 如果是一个对象，那么它最多支持四个属性：fetch、getPublicPath、getDomain、getTemplate，用于替换默认的方法，这里暂不详述。

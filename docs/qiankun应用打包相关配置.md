# Parent Node

- [ROOT](./root.md)
- [qiankun 基础操作](./qiankun基础操作.md)

# Child Node

# qiankun 应用打包相关配置

```js
module.exports = {
  ...
  configureWebpack: { output: { // 把子应用打包成 umd 库格式 library: `micro-app1-[name]`, libraryTarget: 'umd', jsonpFunction: `webpackJsonp_micro-app1` }
  },
  // 以下配置可以修复一些字体文件加载路径问题
  chainWebpack: config => { config .plugin('html') .tap(args => { args[0].name = name; return args }); config.module .rule("fonts") .test(/.(ttf|otf|eot|woff|woff2)$/) .use("url-loader") .loader("url-loader") .tap(options => { options = { // limit: 10000, name: '/static/fonts/[name].[ext]', } return options }) .end();
  },
}
```

- umd 格式的应用会向外暴露指定的生命周期钩子函数，便于 single-spa 解析。
- jsonpFunction 配置是 webpack 打包之后保存在 window 中的 key，只需保证各个子应用不一致即可。
- 其余配置主要是解决一些加载路径问题。

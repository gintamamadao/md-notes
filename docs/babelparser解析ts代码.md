# Parent Node

- [ROOT](./root.md)
- [@babel/parser](./babelparser.md)

# Child Node

# @babel/parser 解析 ts 代码

```js
const ast = parser.parse(code, {
  sourceType: "module",
  plugins: ["typescript"],
});
```

- 指定 sourceType 和 plugins

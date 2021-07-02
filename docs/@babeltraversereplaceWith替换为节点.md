# Parent Node

- [ROOT](./root.md)
- [@babel/traverse](./babeltraverse.md)

# Child Node

# @babel/traverse replaceWith 替换为节点

- replaceWith 的参数就可以通过 babel/types 来获取，
- 比如需要将 function 修改为一个遍历申明，可以这样写

```js
let newNode = t.variableDeclaration("let", [
  t.variableDeclarator(t.identifier("a"), t.stringLiteral("123")),
]);
path.replaceWith(newNode);
```

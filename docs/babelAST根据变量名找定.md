# Parent Node

- [ROOT](./root.md)
- [@babel/parser AST 学习杂记](./@babelparserAST学习杂记.md)

# Child Node

# babel AST 根据变量名找定义

```js
  if (t.isIdentifier(node) && path.scope.hasBinding(node.name)) {
    let bindingNode = path.scope.getBinding(node.name)!.path.node
    if (t.isVariableDeclarator(bindingNode)) {
      bindingNode = bindingNode.init!
    }
    return bindingNode
  }
```

- @babel/traverse 生成的 path 可以提供 api 寻找

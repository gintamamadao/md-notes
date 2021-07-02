# Parent Node

- [ROOT](./root.md)
- [@babel/parser AST 学习杂记](./@babelparserAST学习杂记.md)

# Child Node

# babel AST 获取 ts 类型声明中的子节点

```ts
function getTSNode(node: any) {
  if (
    // <Model> {}
    t.isTSTypeAssertion(node) ||
    // {} as Model
    t.isTSAsExpression(node)
  ) {
    return node.expression;
  }
  return node;
}
```

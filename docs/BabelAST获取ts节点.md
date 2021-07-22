# Parent Node

- [ROOT](./root.md)
- [Babel 学习杂记](./Babel学习杂记.md)

# Child Node

# Babel AST 获取 ts 节点

- 需要注意一些断言场景

```js
export const getTSNode = (node: any) => {
  if (
    // <Model> {}
    types.isTSTypeAssertion(node) ||
    // {} as Model
    types.isTSAsExpression(node)
  ) {
    return node.expression;
  }
  return node;
};
```

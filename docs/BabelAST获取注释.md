# Parent Node

- [ROOT](./root.md)
- [Babel 学习杂记](./Babel学习杂记.md)

# Child Node

# Babel AST 获取注释

- 无法利用 @babel/traverse 去遍历注释
- 可以直接访问 AST 节点

```js
path.node.leadingComments;
path.node.trailingComments;
```

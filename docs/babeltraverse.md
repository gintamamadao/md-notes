# Parent Node

- [ROOT](./root.md)
- [Babel 插件依赖](./Babel插件依赖.md)

# Child Node

- [@babel/traverse replaceWith 替换为节点](./@babeltraversereplaceWith替换为节点.md)

# @babel/traverse

- @babel/traverse 可以用来遍历更新@babel/parser 生成的 AST
- 比如想要寻找所有的 function 就可以这么写。

```js
const parser = require("@babel/parser");
const t = require("@babel/types");
const traverse = require("@babel/traverse").default;

let code = "function a() {}";
const ast = parser.parse(code);
traverse(ast, {
  FunctionDeclaration(path) {
    const node = path.node;
    // 获取函数名称等
    path.replaceWith(); //替换为新的节点
    path.remove(); // 删除当前节点
    path.skip(); //跳过子节点
    let copyNode = t.cloneNode(node); //复制当前节点
    traverse(copyNode, {}, {}, path); // 对子树进行遍历和替换，不影响当前的path
  },
});
```

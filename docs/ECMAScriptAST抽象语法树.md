# Parent Node

- [root](./root.md)
- [ECMAScript 语法](./ECMAScript语法.md)

# Child Node

# ECMAScript AST 抽象语法树

- AST (Abstract Syntax Tree)是抽象语法树英文的缩写
- AST 是对源代码的抽象语法结构的树状表现形式
- AST 语法树每一层都拥有相同的结构，这样的每一层结构也被叫做节点（Node）
- 在不同的场景下，会有不同的解析器将源码解析成抽象语法树
- AST 是源代码的抽象语法结构树状表现形式，Webpack、ESLint、JSX、TypeScript 的编译和模块化规则之间的转化都是通过 AST 来实现对代码的检查、分析以及编译等操作。
- 一个 AST 可以由单一的节点或是成百上千个节点构成。 它们组合在一起可以描述用于静态分析的程序语法。

代码：

```js
let answer = 2 * 3;
```

对应的 AST 语法树：

```json
{
  "type": "Program",
  "body": [
    {
      "type": "VariableDeclaration",
      "declarations": [
        {
          "type": "VariableDeclarator",
          "id": {
            "type": "Identifier",
            "name": "answer"
          },
          "init": {
            "type": "BinaryExpression",
            "operator": "*",
            "left": {
              "type": "Literal",
              "value": 2,
              "raw": "2"
            },
            "right": {
              "type": "Literal",
              "value": 3,
              "raw": "3"
            }
          }
        }
      ],
      "kind": "let"
    }
  ],
  "sourceType": "script"
}
```

# Parent Node

- [ROOT](./root.md)
- [Typescript 语法](./Typescript语法.md)

# Child Node

# Typescript 模块声明

- 可以通过 declare module 'somePath' 声明一个全局模块的方式，来解决查找模块路径的问题。

```ts
// global.d.ts
declare module "foo" {
  // some variable declarations
  export var bar: number;
}
```

接着 ：

```ts
// anyOtherTsFileInYourProject.ts
import * as foo from "foo";
// TypeScript 将假设（在没有做其他查找的情况下）
// foo 是 { bar: number }
```

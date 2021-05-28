# Parent Node

- [ROOT](./root.md)
- [Typescript 学习杂记](./Typescript学习杂记.md)

# Child Node

# ts 无法重新声明块范围变量

- 环境 d.ts 文件中声明了许多全局变量，例如 web 环境
- ts 不能将 commonjs 封装声明的当做一个闭包模块，导致了变量的全局声明
- 归根到底是在某个地方做了全局声明
- 可修改配置，使某环境 d.ts 可以在 lib 中配置是否声明

```ts
  "compilerOptions": {
    "lib": ["esnext"],
  }
```

- 可以让 commonjs 伪装成 esmodule

```ts
export {};
```

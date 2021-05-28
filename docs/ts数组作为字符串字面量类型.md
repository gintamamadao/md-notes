# Parent Node

- [ROOT](./root.md)
- [Typescript 学习杂记](./Typescript学习杂记.md)

# Child Node

# ts 数组作为字符串字面量类型

- declare 必须有

```ts
declare const ButtonTypes: [
  "default",
  "primary",
  "ghost",
  "dashed",
  "link",
  "text"
];
declare type ButtonType = typeof ButtonTypes[number];
```

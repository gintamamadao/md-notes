# Parent Node

- [/](./root.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)
- [Typescript 内置类型](./Typescript内置类型.md)

# Child Node

# Typescript 内置类型 Parameters

```ts
/**
 * Obtain the parameters of a function type in a tuple
 */
type Parameters<T extends (...args: any) => any> = T extends (
  ...args: infer P
) => any
  ? P
  : never;
```

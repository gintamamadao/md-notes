# Parent Node

- [ROOT](./root.md)
- [Typescript 内置类型](./Typescript内置类型.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)

# Child Node

# Typescript 内置类型 ReturnType

```ts
/**
 * Obtain the return type of a function type
 */
type ReturnType<T extends (...args: any) => any> = T extends (
  ...args: any
) => infer R
  ? R
  : any;
```

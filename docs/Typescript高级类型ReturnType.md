# Parent Node

- [root](./root.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)

# Child Node

# Typescript 高级类型 ReturnType

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

# Parent Node

- [ROOT](./root.md)
- [Typescript 条件类型 infer](./Typescript条件类型infer.md)
- [Typescript 内置类型](./Typescript内置类型.md)

# Child Node

# Typescript 内置类型 InstanceType

```ts
/**
 * Obtain the return type of a constructor function type
 */
type InstanceType<T extends new (...args: any) => any> = T extends new (
  ...args: any
) => infer R
  ? R
  : any;
```

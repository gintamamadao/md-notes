# Parent Node

- [/](./root.md)
- [../](./Typescript类型推断infer.md)
- [../](./Typescript条件类型infer.md)

# Child Node

# Detail

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

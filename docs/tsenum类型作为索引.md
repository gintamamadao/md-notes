# Parent Node

- [ROOT](./root.md)
- [Typescript 学习杂记](./Typescript学习杂记.md)

# Child Node

# ts enum 类型作为索引

```ts
enum Options {
  ONE = "one",
  TWO = "two",
  THREE = "three",
}
interface OptionRequirement {
  someBool: boolean;
  someString: string;
}
type OptionRequirements = {
  [key in Options]: OptionRequirement; // Note that "key in".
};
```

- 类似于

```ts
type OptionRequirements = Record<Options, OptionRequirement>;
```

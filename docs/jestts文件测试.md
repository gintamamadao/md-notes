# Parent Node

- [ROOT](./root.md)
- [jest 学习杂记](./jest学习杂记.md)

# Child Node

# jest ts 文件测试

```sh
yarn add -D typescript jest ts-jest @types/jest
```

- jest.config.js

```js
module.exports = {
  transform: {
    "^.+\\.tsx?$": "ts-jest",
  },
  testRegex: "(/__tests__/.*|(\\.|/)(test|spec))\\.(jsx?|tsx?)$",
  moduleFileExtensions: ["ts", "tsx", "js", "jsx", "json", "node"],
};
```

# Parent Node

- [ROOT](./root.md)
- [jest config](./jestconfig.md)

# Child Node

# jest config collectCoverageFrom

- 可以用一个 通配模式 的数组来指出仅哪些文件需要收集覆盖率信息。
- 如果一个文件匹配上指定的模式，即使没有关于它的测试用例存在，或也没有任何测试用例依赖它，它的覆盖率信息也将被收集。

```sh
{
  "collectCoverageFrom" : ["**/*.{js,jsx}", "!**/node_modules/**", "!**/vendor/**"]
}
```

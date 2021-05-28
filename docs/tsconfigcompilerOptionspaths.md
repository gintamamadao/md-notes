# Parent Node

- [ROOT](./root.md)
- [Typescript tsconfig 配置](./Typescripttsconfig配置.md)

# Child Node

# tsconfig compilerOptions paths

- 可以设置路径别名
- 不可以没有 baseUrl 配置

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"],
      "@@/*": ["src/.umi/*"]
    }
  }
}
```

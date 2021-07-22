# Parent Node

- [ROOT](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# `#__PURE__`

- 用于代码压缩 tree shaking
- 当变量没有用到会把变量删掉，但却不会把左边的方法调用删掉
- Uglify 默认自定义的方法都是有 side effects 的，
- 所以它不会帮我们删除方法的调用，
- 除非我们给调用方法注释 `#__PURE__` 或者 `@__PURE__`

# Parent Node

- [ROOT](./root.md)
- [ECMAScript 模块封装](./ECMAScript模块封装.md)

# Child Node

- [ES 模块 import 用法](./ES模块import用法.md)
- [ES 模块 export 用法](./ES模块export用法.md)

# ES 模块封装标准

- ES6 模块是动态引用，并且不会缓存值，模块里面的变量绑定其所在的模块
- JS 引擎对脚本静态分析的时候，遇到模块加载命令 import，就会生成一个只读引用。
- 等到脚本真正执行时，再根据这个只读引用，到被加载的那个模块里面去取值。
- 原始值变了，import 加载的值也会跟着变。
- 引入文件的大小写错误的是可以导致编译通过，但更新不通过

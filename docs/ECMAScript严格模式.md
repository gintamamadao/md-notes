# Parent Node

- [/](./root.md)
- [../](./ECMAScript基础语法.md)

# Child Node

# Detail

- 通过在脚本的最顶端放上一个特定语句 "use strict";
- 整个脚本就可开启严格模式语法。

## 表现

- 严格模式会使引起静默失败(silently fail,注:不报错也没有任何效果)的赋值操作抛出异常
- 严格模式下的 eval 不再为上层范围(surrounding scope,注:包围 eval 代码块的范围)引入新变量
- 严格模式禁止删除声明变量
- 在严格模式中一部分字符变成了保留的关键字。
- 这些字符包括 implements, interface, let, package, private, protected, public, static 和 yield。
- 在严格模式下，你不能再用这些名字作为变量名或者形参名。
- 严格模式下 arguments 和参数值是完全独立的，非严格下修改是会相互影响的

## 优势

- 消除 Javascript 语法的一些不合理、不严谨之处，减少一些怪异行为;
- 消除代码运行的一些不安全之处，保证代码运行的安全；
- 提高编译器效率，增加运行速度；
- 为未来新版本的 Javascript 做好铺垫。

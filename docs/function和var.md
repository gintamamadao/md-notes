# Parent Node

- [ROOT](./root.md)
- [ECMAScript 变量声明](./ECMAScript变量声明.md)

# Child Node

# function 和 var

- function 声明和 var 声明会被提前到代码最前面定义
- 在提前到最前面定义时, var 声明仅仅是定义变量, 只有执行到相应代码才会执行变量赋值, 所以最前面时变量值为 `undefined`
- 在提前到最前面定义时, function 就执行变量赋值, 所以最前面时变量值已经是函数。所以定义函数在最开始和最后没有差别
- var、function 声明的全局变量，会成为顶层对象的属性
- 要注意在函数作用域里，也会有变量提升这件事情，在块状作用域里不会
- 用 var 声明的全局变量，是不可以用 delete 操作符删除的

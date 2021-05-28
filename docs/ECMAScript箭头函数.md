# Parent Node

- [root](./root.md)
- [ECMAScript 语法](./ECMAScript语法.md)

# Child Node

# Detail

- 箭头函数在定义时已经绑定了上下文, 就是函数的 this 总是指向定义时所在环境的 this, 而不是函数的调用者。
- 无法通过 apply, call, bind 等改变函数体内的 this
- 不可以当作构造函数, 也就是说, 不可以使用 new 命令, 否则会抛出一个错误
- 不可以使用 arguments 对象, 该对象在函数体内不存在。如果要用, 可以用 rest 参数代替
- 不可以使用 yield 命令, 因此箭头函数不能用作 Generator 函数
- es6 中 class 的属性箭头函数的指向是用这个类新建的对象

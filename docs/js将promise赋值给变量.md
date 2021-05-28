# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

- 将 promise 赋值给变量，不能在传入 promise 的函数里调用变量本身
- 因为传入 promise 的函数是立即执行的，先于赋值，所以变量此时还没有进行变量声明

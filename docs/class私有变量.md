# Parent Node

- [root](./root.md)
- [ECMAScript class](./ECMAScriptclass.md)

# Child Node

# class 私有变量

- 使用 # 符号表示类的私有变量

```js
class Counter {
  #x = 0;

  #increment() {
    this.#x++;
  }
}
const c = new Counter();
c.#increment(); // 报错
```

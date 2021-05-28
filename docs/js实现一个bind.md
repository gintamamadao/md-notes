# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

```js
Function.prototype.mycall = function (context) {
  //判断是否传入指定的对象
  context = context || {};
  //拿到传入的参数
  let args = [...arguments].slice(1);
  //把调用的函数添加到对象中
  context.__fn = this;
  //执行函数
  let result = context.__fn(...args);
  //执行函数后，从对象中删除掉函数
  delete context.__fn;
  return result;
};

function Test() {
  console.log(this.name);
  console.log(this.sex);
}

let obj = {
  name: "李四",
  sex: "男",
};

Test.mycall(obj);
```

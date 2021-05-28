# Parent Node

- [ROOT](./root.md)
- [ECMAScript 原型与继承](./ECMAScript原型与继承.md)

# Child Node

# js 寄生式继承

- 创建一个仅用于封装继承过程的函数，该函数在内部以某种方式来增强对象，最后返回这个对象

```js
function createPerson(original) {
  var clone = Object.create(original);
  clone.sayGood = function () {
    alert("good");
  };
  return clone;
}
```

- 此模式的缺点是做不到函数复用
- 创建子类型的实例时，没法传参给被继承类型。因为被继承类型已经实例化了

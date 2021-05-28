# Parent Node

- [ROOT](./root.md)
- [ECMAScript 原型与继承](./ECMAScript原型与继承.md)

# Child Node

# js 寄生组合式继承

- 通过借用构造函数来继承属性，通过原型链的混成形式来继承方法。
- 本质上，就是使用寄生式继承来继承超类型的原型，然后再将结果指定给子类型的原型

```js
function SuperType(name) {
  this.name = name;
  this.colors = ["red", "green", "blue"];
}
SuperType.prototype.sayName = function () {
  alert(this.name);
};
function SubType(name, age) {
  SuperType.call(this, name);
  this.age = age;
}
var anotherPrototype = Object.create(SuperType.prototype);
anotherPrototype.constructor = SubType;
SubType.prototype = anotherPrototype;
```

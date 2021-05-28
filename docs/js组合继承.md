# Parent Node

- [root](./root.md)
- [ECMAScript 原型与继承](./ECMAScript原型与继承.md)

# Child Node

# Detail

- 将原型链和借用构造函数的技术组合到一块。使用原型链实现对原型属性和方法的继承，而通过借用构造函数来实现对实例属性的继承。
- 这样，既通过在原型上定义方法实现了函数复用，又能够保证每个实例都有自己的属性。

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
SubType.prototype = new SuperType();
```

## 缺点

- 组合继承避免了原型链和借用构造函数的缺陷，融合了它们的优点，成为 javascript 中最常用的继承模式。
- 而且，使用 instanceof 操作符和 isPrototype() 方法也能够用于识别基于组合继承创建的对象。
- 无论在什么情况下，都会调用两次超类型构造函数：一次是在创建子类型原型的时候，另一次是在子类型构造函数内部。

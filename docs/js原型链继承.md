# Parent Node

- [/](./root.md)
- [ECMAScript 原型与继承](./ECMAScript原型与继承.md)

# Child Node

# Detail

- 让子对象的原型指向父对象的实例，父对象的原型指向爷爷对象的实例，依次类推，就形成了原型链

```js
function Animal(newAge) {
  this.age = newAge;
}
function Person(newId) {
  this.id = newId;
}
Person.prototype = new Animal(18);
```

## 缺点

- 在通过原型来实现继承时，原型实际上会变成另一个类型的实例。原先的实例静态属性也就顺理成章地变成了现在的原型属性
- 创建子类型的实例时，没法传参给被继承类型。因为被继承类型已经实例化了

# Parent Node

- [root](./root.md)
- [ECMAScript 原型与继承](./ECMAScript原型与继承.md)

# Child Node

# Detail

- 在子类的构造函数中，通过 apply ( ) 或 call ( )的形式，调用父类构造函数，以实现继承

```js
function Person() {
  this.sex = "male";
}
function Student(studentID) {
  this.studentID = studentID;
  Person.call(this);
}
```

- 每个实例都拷贝一份，占用内存大，尤其是方法过多的时候。（函数复用又无从谈起了，本来我们用 prototype 就是解决复用问题的）
- 方法都作为了实例自己的方法，当需求改变，要改动其中的一个方法时，之前所有的实例，他们的该方法都不能及时作出更新。只有后面的实例才能访问到新方法。

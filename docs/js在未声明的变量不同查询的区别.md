# Parent Node

- [root](./root.md)
- [js 变量查询](./js变量查询.md)

# Child Node

# Detail

- LHS 查询会导致自动隐式地创建一个全局变量（非严格模式下），或者抛出 ReferenceError 异常（严格模式下）
- RHS 查询会抛出 ReferenceError 异常。因为无法找到变量本身，进而无法找到变量的值，所以报错

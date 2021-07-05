# Parent Node

- [ROOT](./root.md)
- [jest api](./jestapi.md)

# Child Node

# jest toBeCalledWith

- 检查一个模拟函数它被调用时传入的参数

```js
function randocall(fn) {
  return fn(Math.floor(Math.random() * 6 + 1));
}

test("randocall calls its callback with a number", () => {
  const mock = jest.fn();
  randocall(mock);
  expect(mock).toBeCalledWith(expect.any(Number));
});
```

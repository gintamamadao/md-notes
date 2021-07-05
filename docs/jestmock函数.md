# Parent Node

- [ROOT](./root.md)
- [jest api](./jestapi.md)

# Child Node

# jest mock 函数

```js
const mockFunc = jest.fn();
const forEach = (array, callback) => {
  for (let index = 0; index < array.length; index++) {
    const element = array[index];
    callback(element);
  }
};

test("should call callback when forEach", () => {
  const mockFun = jest.fn(); // mock 函数
  const array = [1, 2];

  forEach(array, mockFun); // 用mock函数代替真实的回调函数

  console.log(mockFun.mock);
  expect(mockFun.mock.calls.length).toBe(2);
});
```

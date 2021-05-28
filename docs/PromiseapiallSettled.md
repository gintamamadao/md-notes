# Parent Node

- [root](./root.md)
- [Promise api](./Promiseapi.md)

# Child Node

# Detail

```js
promise_1 = Promise.resolve("hello");
promise_2 = new Promise((resolve, reject) =>
  setTimeout(reject, 200, "problem")
);

Promise.allSettled([promise_1, promise_2]).then(
  ([promise_1_result, promise_2_result]) => {
    console.log(promise_1_result); // 输出：{status: 'fulfilled', value: 'hello'}
    console.log(promise_2_result); // 输出：{status: 'rejected', reason: 'problem'}
  }
);
```

- 等待多个 promise 返回结果时，我们可以用 Promise.all(\[promise_1, promise_2])。
- 但问题是，如果其中一个请求失败了，就会抛出错误。然而，有时候我们希望某个请求失败后，其他请求的结果能够正常返回。针对这种情况 ES11 引入了 Promise.allSettled 。

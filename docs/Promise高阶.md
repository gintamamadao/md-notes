# Parent Node

- [/](./root.md)
- [../](./ECMAScriptPromise.md)

# Child Node

# Detail

- promise 里如果返回的结果也是 promise, 那 then 会自动跟踪这个 promise 的最后的值

```js
const a = new Promise((r) => {
  r(
    new Promise((r) => {
      r(
        new Promise((r) => {
          r(
            new Promise((r) => {
              r(
                new Promise((r) => {
                  r(2);
                })
              );
            })
          );
        })
      );
    })
  );
});

a.then((e) => {
  console.log(e, "e");
  return new Promise((r) => {
    r(
      new Promise((r) => {
        r(
          new Promise((r) => {
            r(
              new Promise((r) => {
                r(2);
              })
            );
          })
        );
      })
    );
  });
}).then((e) => {
  console.log(e, "e22");
});
```

# Parent Node

- [/](./root.md)
- [../](./ECMAScript学习杂记.md)

# Child Node

# Detail

```js
const file = data.file;
const imgFile = new FileReader();
imgFile.readAsDataURL(file);
const imgData = await new Promise((resolve) => {
  imgFile.onload = () => {
    resolve(imgFile.result);
  };
});
```

# Parent Node

- [ROOT](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# js input 导入的文件转换成 base64

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

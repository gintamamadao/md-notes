# Parent Node

- [/](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# Detail

- 用 a 标签下载
- responseType 设置成 blob

```js
// var blob = new Blob([res], { type: 'application/vnd.ms-excel' });
const blob = new Blob([res], { type: "application/octet-stream" });
// 根据传入的参数b创建一个指向该参数对象的URL
const url = URL.createObjectURL(blob);
const link = document.createElement("a");
// 设置导出的文件名
link.download = `any.xlsx`;
link.href = url;
// 点击获取文件
link.click();
```

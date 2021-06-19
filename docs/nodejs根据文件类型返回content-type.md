# Parent Node

- [ROOT](./root.md)
- [NodeJS 学习杂记](./Node学习杂记.md)

# Child Node

# nodejs 根据文件类型返回 content-type

```js
const mime = require("mime-types"); //需npm安装

let filePath = path.join(__dirname, ctx.url); //图片地址
let mimeType = mime.lookup(filePath); //读取图片文件类型
ctx.set("content-type", mimeType); //设置返回类型
```

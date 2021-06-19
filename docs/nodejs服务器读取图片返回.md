# Parent Node

- [ROOT](./root.md)
- [NodeJS 学习杂记](./Node学习杂记.md)

# Child Node

# nodejs 服务器读取图片返回

```js
response.writeHead(200, { "Content-Type": "image/png" });
var imageFilePath = pathname.substr(1);
var stream = fs.createReadStream(imageFilePath);
var responseData = []; //存储文件流
if (stream) {
  //判断状态
  stream.on("data", function (chunk) {
    responseData.push(chunk);
  });
  stream.on("end", function () {
    var finalData = Buffer.concat(responseData);
    response.write(finalData);
    response.end();
  });
}
```

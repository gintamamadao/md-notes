# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# js canvas 压缩图片

```js

  let cvs = document.createElement("canvas") as any;
  let quality = 0.9;

  let ctx = cvs.getContext("2d") as any;

  const size = getImgWH(w, h, maxWidth, maxHeight);

  cvs.width = size.w;
  cvs.height = size.h;

  // 填充白色背景
  ctx.fillStyle = fillBgColor;
  ctx.fillRect(0, 0, size.w, size.h);

  // 将图片绘制到Canvas上，从原点0,0绘制到w,h
  ctx.drawImage(image, 0, 0, size.w, size.h);

  let dataUrl = cvs.toDataURL(`image/${fileType}`, quality);

```

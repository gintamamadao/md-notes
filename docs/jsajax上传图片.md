# Parent Node

- [root](./root.md)
- [ECMAScript 学习杂记](./ECMAScript学习杂记.md)

# Child Node

# js ajax 上传图片

```js
var xhr = new XMLHttpRequest();
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4 && xhr.status === 200) {
    console.log(xhr.responseText);
    info.innerHTML = xhr.responseText;
  }
};

xhr.upload.addEventListener(
  "progress",
  function (event) {
    if (event.lengthComputable) {
      progress.style.width =
        Math.ceil((event.loaded * 100) / event.total) + "%";
    }
  },
  false
);

xhr.open("POST", "./upload");
xhr.send(formData);
```

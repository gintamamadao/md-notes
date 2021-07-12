# Parent Node

- [ROOT](./root.md)
- [got](./got.md)

# Child Node

# got 发送 formData 请求

```js
import fs from "fs";
import got from "got";
import FormData from "form-data";

const form = new FormData();

form.append("my_file", fs.createReadStream("/foo/bar.jpg"));

got.post("https://example.com", {
  body: form,
  headers: {
    "Content-Type": "multipart/form-data",
  },
});
```

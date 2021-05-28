# Parent Node

- [ROOT](./root.md)
- [ECMAScript class](./ECMAScriptclass.md)

# Child Node

# class static

```js
class Colors {
  // public static 字段
  static red = "#ff0000";
  static green = "#00ff00";

  // private static 字段
  static #secretColor = "#f0f0f0";
}

font.color = Colors.red;
font.color = Colors.#secretColor; // 出错
```

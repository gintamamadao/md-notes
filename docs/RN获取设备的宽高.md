# Parent Node

- [ROOT](./root.md)
- [RN 学习杂记](./RN学习杂记.md)

# Child Node

# RN 获取设备的宽高

- 我们使用 Dimensions API 可以得到手机屏幕的宽和高
- 当设备横置时，通过 Dimensions API 取到的宽大于高。
- 当设备竖置时，通过 Dimensions API 取到的宽小于高。


```js
const windowWidth = Dimensions.get('window').width;
const windowHeight = Dimensions.get('window').height;
```
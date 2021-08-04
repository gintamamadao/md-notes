# Parent Node

- [ROOT](./root.md)
- [RN hooks](./RNhooks.md)

# Child Node

# RN useWindowDimensions

- useWindowDimensions 当屏幕尺寸改变时自动更新 width 和 height 值。
- 您可以像这样获取应用程序窗口的宽度和高度：

```
import { useWindowDimensions } from 'react-native' ; 
const windowWidth = useWindowDimensions().width;
const windowHeight = useWindowDimensions().height;
```
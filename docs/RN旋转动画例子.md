# Parent Node

- [ROOT](./root.md)
- [RN 学习杂记](./RN学习杂记.md)

# Child Node

# RN 旋转动画例子

```js
import React, { FC, useRef, useEffect } from "react";
import { View, Animated } from "react-native";

import styles from "./styles";

export const Loading: FC = () => {
  const spinAnim = useRef(new Animated.Value(0)).current;

  useEffect(() => {
    const spin = () => {
      spinAnim.setValue(0);
      Animated.timing(spinAnim, {
        toValue: 360,
        duration: 1000,
      }).start(() => spin());
    };
    spin();
  }, []);

  return (
    <View style={styles.loadingView}>
      <Animated.Image
        style={[
          styles.loadingIcon,
          {
            transform: [
              {
                rotate: spinAnim.interpolate({
                  inputRange: [0, 360],
                  outputRange: ["0deg", "360deg"],
                }),
              },
            ],
          },
        ]}
        source={require("./assets/loading.png")}
      />
    </View>
  );
};
```

- start 执行就是数值开始变化，相关数值变化就触发动画
- start 的回调函数就是动画接受的回调，可以利用做循环执行
- 循环执行需要注意一定要把值初始化 `spinAnim.setValue(0)`

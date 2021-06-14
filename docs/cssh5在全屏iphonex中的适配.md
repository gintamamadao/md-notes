# Parent Node

- [ROOT](./root.md)
- [CSS 学习杂记](./CSS学习杂记.md)

# Child Node

# css h5 在全屏 iphonex 中的适配

- 可以用 js 判断是否是 iphone X 然后在顶层加上一个类名

- 也可以用特殊值

- safe-area-inset-left：安全区域距离左边边界距离, 一般情况下是 0

- safe-area-inset-right：安全区域距离右边边界距离, 一般情况下是 0

- safe-area-inset-top：安全区域距离顶部边界距离, 在刘海全屏的时候 top 为 44px

- safe-area-inset-bottom：安全区域距离底部边界距离,刘海全屏的条件下是 34px

```css
@mixin iphonex-css {
  padding-top: constant(safe-area-inset-top); //为导航栏+状态栏的高度 88px
  padding-top: env(safe-area-inset-top); //为导航栏+状态栏的高度 88px
  padding-left: constant(safe-area-inset-left); //如果未竖屏时为0
  padding-left: env(safe-area-inset-left); //如果未竖屏时为0
  padding-right: constant(safe-area-inset-right); //如果未竖屏时为0
  padding-right: env(safe-area-inset-right); //如果未竖屏时为0
  padding-bottom: constant(safe-area-inset-bottom); //为底下圆弧的高度 34px
  padding-bottom: env(safe-area-inset-bottom); //为底下圆弧的高度 34px
}
@mixin iphonex-support {
  @supports (bottom: constant(safe-area-inset-top)) or
    (bottom: env(safe-area-inset-top)) {
    body.iphonex {
      @include iphonex-css;
    }
  }
}
```

```css
@mixin iphonex-css {
  padding-top: constant(safe-area-inset-top); //为导航栏+状态栏的高度 88px
  padding-top: env(safe-area-inset-top); //为导航栏+状态栏的高度 88px
  padding-left: constant(safe-area-inset-left); //如果未竖屏时为0
  padding-left: env(safe-area-inset-left); //如果未竖屏时为0
  padding-right: constant(safe-area-inset-right); //如果未竖屏时为0
  padding-right: env(safe-area-inset-right); //如果未竖屏时为0
  padding-bottom: constant(safe-area-inset-bottom); //为底下圆弧的高度 34px
  padding-bottom: env(safe-area-inset-bottom); //为底下圆弧的高度 34px
}
// iphonex 适配
@mixin iphonex-media {
  @media only screen and (device-width: 375px) and (device-height: 812px) and (-webkit-device-pixel-ratio: 3) {
    body.iphonex {
      @include iphonex-css;
    }
  }
}
```

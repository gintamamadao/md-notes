# Parent Node

- [ROOT](./root.md)
- [CSS 学习杂记](./CSS学习杂记.md)

# Child Node

# css dialog 新动画例子

```less
.wrapper {
  margin: 0 auto;
  &.sssss-dialog {
    width: 100vw;
    position: absolute;
    bottom: 0;
    overflow: hidden;

    .effect() {
      animation-duration: 0.6s;
      animation-fill-mode: both;
    }

    &-slide-up-enter,
    &-slide-up-appear {
      .effect();
      transform: translateY(100%);
      animation-timing-function: ease-in-out;
      animation-play-state: paused;
    }

    &-slide-up-leave {
      .effect();
      animation-timing-function: ease-in-out;
      animation-play-state: paused;
    }

    &-slide-up-enter&-slide-up-enter-active,
    &-slide-up-appear&-slide-up-appear-active {
      animation-name: rcDialogSlideUpIn;
      animation-play-state: running;
    }

    &-slide-up-leave&-slide-up-leave-active {
      animation-name: rcDialogSlideUpOut;
      animation-play-state: running;
    }
  }
  .bs_slider_box {
    background-color: #fff;
    border-radius: 4px 4px 0 0;
    height: 500px;
  }
}

.bs_slider_wrap.sssss-dialog-wrap {
  overflow: hidden;
}

@keyframes rcDialogSlideUpIn {
  0% {
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}
@keyframes rcDialogSlideUpOut {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(100%);
  }
}
```

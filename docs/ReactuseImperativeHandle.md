# Parent Node

- [ROOT](./root.md)
- [React hooks](./Reacthooks.md)

# Child Node

# React useImperativeHandle

- useImperativeHandle 可以让你在使用 ref 时自定义暴露给父组件的实例值
- useImperativeHandle 应当与 forwardRef 一起使用
- 在介绍 useImperativeHandle 之前一定要清楚 React 关于 ref 转发（也叫透传）的知识点，
- 是使用 React.forwardRef 方法实现的，该方法返回一个组件，参数为函数（props callback，并不是函数组件），
- 函数的第一个参数为父组件传递的 props，第二给参数为父组件传递的 ref，
- 其目的就是希望可以在封装组件时，外层组件可以通过 ref 直接控制内层组件或元素的行为。

```js
import React, { useRef, useImperativeHandle } from "react";
import ReactDOM from "react-dom";

const FancyInput = React.forwardRef((props, ref) => {
  const inputRef = useRef();
  useImperativeHandle(ref, () => ({
    focus: () => {
      inputRef.current.focus();
    },
  }));

  return <input ref={inputRef} type="text" />;
});

const App = (props) => {
  const fancyInputRef = useRef();

  return (
    <div>
      <FancyInput ref={fancyInputRef} />
      <button onClick={() => fancyInputRef.current.focus()}>
        父组件调用子组件的 focus
      </button>
    </div>
  );
};
```

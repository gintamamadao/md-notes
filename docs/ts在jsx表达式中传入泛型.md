# Parent Node

- [ROOT](./root.md)
- [Typescript 学习杂记](./Typescript学习杂记.md)

# Child Node

# ts 在 jsx 表达式中传入泛型

```jsx
class Bar<T> extends React.Component<Props<T>> {
  render() {
    return <div>{this.props.content}</div>;
  }
}

 <Bar<string> content={"hello"}></Bar>
```

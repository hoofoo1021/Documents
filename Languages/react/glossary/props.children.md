# props.children

`props.children` is available on every component. It contains the content between the opening and closing tags of a component. For example:

```
<Welcome>Hello world!</Welcome>
```

The string `Hello world!` is available in `props.children` in the `Welcome` component:

```
function Welcome(props) {
  return <p>{props.children}</p>;
}
```

For components defined as classes, use `this.props.children`:

```
class Welcome extends React.Component {
  render() {
    return <p>{this.props.children}</p>;
  }
}
```

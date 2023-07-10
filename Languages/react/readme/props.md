# 🌵 props

`props` are inputs to a React component. They are data passed down from a parent component to a child component.

Remember that `props` are readonly. They should not be modified in any way:

```
// Wrong!
props.number = 42;
```

If you need to modify some value in response to user input or a network response, use `state` instead.

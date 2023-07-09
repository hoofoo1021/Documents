# static getDerivedStateFromError()

#### `static getDerivedStateFromError()` <a href="#static-getderivedstatefromerror" id="static-getderivedstatefromerror"></a>

```
static getDerivedStateFromError(error)
```

This lifecycle is invoked after an error has been thrown by a descendant component. It receives the error that was thrown as a parameter and should return a value to update state.

```
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {
    // Update state so the next render will show the fallback UI.
    return { hasError: true };
  }

  render() {
    if (this.state.hasError) {
      // You can render any custom fallback UI
      return <h1>Something went wrong.</h1>;
    }

    return this.props.children;
  }
}
```

> Note
>
> `getDerivedStateFromError()` is called during the “render” phase, so side-effects are not permitted. For those use cases, use `componentDidCatch()` instead.

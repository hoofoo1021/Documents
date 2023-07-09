# UNSAFE\_componentWillUpdate()

#### `UNSAFE_componentWillUpdate()` <a href="#unsafe_componentwillupdate" id="unsafe_componentwillupdate"></a>

```
UNSAFE_componentWillUpdate(nextProps, nextState)
```

> Note
>
> This lifecycle was previously named `componentWillUpdate`. That name will continue to work until version 17. Use the [`rename-unsafe-lifecycles` codemod](https://github.com/reactjs/react-codemod#rename-unsafe-lifecycles) to automatically update your components.

`UNSAFE_componentWillUpdate()` is invoked just before rendering when new props or state are being received. Use this as an opportunity to perform preparation before an update occurs. This method is not called for the initial render.

Note that you cannot call `this.setState()` here; nor should you do anything else (e.g. dispatch a Redux action) that would trigger an update to a React component before `UNSAFE_componentWillUpdate()` returns.

Typically, this method can be replaced by `componentDidUpdate()`. If you were reading from the DOM in this method (e.g. to save a scroll position), you can move that logic to `getSnapshotBeforeUpdate()`.

> Note
>
> `UNSAFE_componentWillUpdate()` will not be invoked if [`shouldComponentUpdate()`](https://devdocs.io/react/react-component#shouldcomponentupdate) returns false.

### Other APIs <a href="#other-apis-1" id="other-apis-1"></a>

Unlike the lifecycle methods above (which React calls for you), the methods below are the methods _you_ can call from your components.

There are just two of them: `setState()` and `forceUpdate()`.

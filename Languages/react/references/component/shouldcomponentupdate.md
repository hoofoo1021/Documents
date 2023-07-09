# shouldComponentUpdate()

#### `shouldComponentUpdate()` <a href="#shouldcomponentupdate" id="shouldcomponentupdate"></a>

```
shouldComponentUpdate(nextProps, nextState)
```

Use `shouldComponentUpdate()` to let React know if a component’s output is not affected by the current change in state or props. The default behavior is to re-render on every state change, and in the vast majority of cases you should rely on the default behavior.

`shouldComponentUpdate()` is invoked before rendering when new props or state are being received. Defaults to `true`. This method is not called for the initial render or when `forceUpdate()` is used.

This method only exists as a [**performance optimization**](https://devdocs.io/react/optimizing-performance)**.** Do not rely on it to “prevent” a rendering, as this can lead to bugs. **Consider using the built-in** [**`PureComponent`**](https://devdocs.io/react/react-api#reactpurecomponent) instead of writing `shouldComponentUpdate()` by hand. `PureComponent` performs a shallow comparison of props and state, and reduces the chance that you’ll skip a necessary update.

If you are confident you want to write it by hand, you may compare `this.props` with `nextProps` and `this.state` with `nextState` and return `false` to tell React the update can be skipped. Note that returning `false` does not prevent child components from re-rendering when _their_ state changes.

We do not recommend doing deep equality checks or using `JSON.stringify()` in `shouldComponentUpdate()`. It is very inefficient and will harm performance.

Currently, if `shouldComponentUpdate()` returns `false`, then [`UNSAFE_componentWillUpdate()`](https://devdocs.io/react/react-component#unsafe\_componentwillupdate), [`render()`](https://devdocs.io/react/react-component#render), and [`componentDidUpdate()`](https://devdocs.io/react/react-component#componentdidupdate) will not be invoked. In the future React may treat `shouldComponentUpdate()` as a hint rather than a strict directive, and returning `false` may still result in a re-rendering of the component.

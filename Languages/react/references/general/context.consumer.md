# Context.Consumer

#### `Context.Consumer` <a href="#contextconsumer" id="contextconsumer"></a>

```
<MyContext.Consumer>
  {value => /* render something based on the context value */}
</MyContext.Consumer>
```

A React component that subscribes to context changes. Using this component lets you subscribe to a context within a [function component](https://devdocs.io/react/components-and-props#function-and-class-components).

Requires a [function as a child](https://devdocs.io/react/render-props#using-props-other-than-render). The function receives the current context value and returns a React node. The `value` argument passed to the function will be equal to the `value` prop of the closest Provider for this context above in the tree. If there is no Provider for this context above, the `value` argument will be equal to the `defaultValue` that was passed to `createContext()`.

> Note
>
> For more information about the ‘function as a child’ pattern, see [render props](https://devdocs.io/react/render-props).

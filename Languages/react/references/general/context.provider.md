# 🍕 Context.Provider

#### `Context.Provider` <a href="#contextprovider" id="contextprovider"></a>

```
<MyContext.Provider value={/* some value */}>
```

Every Context object comes with a Provider React component that allows consuming components to subscribe to context changes.

The Provider component accepts a `value` prop to be passed to consuming components that are descendants of this Provider. One Provider can be connected to many consumers. Providers can be nested to override values deeper within the tree.

All consumers that are descendants of a Provider will re-render whenever the Provider’s `value` prop changes. The propagation from Provider to its descendant consumers (including [`.contextType`](https://devdocs.io/react/context#classcontexttype) and [`useContext`](https://devdocs.io/react/hooks-reference#usecontext)) is not subject to the `shouldComponentUpdate` method, so the consumer is updated even when an ancestor component skips an update.

Changes are determined by comparing the new and old values using the same algorithm as [`Object.is`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/is#Description).

> Note
>
> The way changes are determined can cause some issues when passing objects as `value`: see [Caveats](https://devdocs.io/react/context#caveats).

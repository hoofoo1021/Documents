# 🌵 render()

#### `render()` <a href="#render" id="render"></a>

```
render(element, container[, callback])
```

> Note:
>
> `render` has been replaced with `createRoot` in React 18. See [createRoot](https://devdocs.io/react/react-dom-client#createroot) for more info.

Render a React element into the DOM in the supplied `container` and return a [reference](https://devdocs.io/react/refs-and-the-dom) to the component (or returns `null` for [stateless components](https://devdocs.io/react/components-and-props#function-and-class-components)).

If the React element was previously rendered into `container`, this will perform an update on it and only mutate the DOM as necessary to reflect the latest React element.

If the optional callback is provided, it will be executed after the component is rendered or updated.

> Note:
>
> `render()` controls the contents of the container node you pass in. Any existing DOM elements inside are replaced when first called. Later calls use React’s DOM diffing algorithm for efficient updates.
>
> `render()` does not modify the container node (only modifies the children of the container). It may be possible to insert a component to an existing DOM node without overwriting the existing children.
>
> `render()` currently returns a reference to the root `ReactComponent` instance. However, using this return value is legacy and should be avoided because future versions of React may render components asynchronously in some cases. If you need a reference to the root `ReactComponent` instance, the preferred solution is to attach a [callback ref](https://devdocs.io/react/refs-and-the-dom#callback-refs) to the root element.
>
> Using `render()` to hydrate a server-rendered container is deprecated. Use [`hydrateRoot()`](https://devdocs.io/react/react-dom-client#hydrateroot) instead.

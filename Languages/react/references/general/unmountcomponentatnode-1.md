# unmountComponentAtNode()

#### `unmountComponentAtNode()` <a href="#unmountcomponentatnode" id="unmountcomponentatnode"></a>

```
unmountComponentAtNode(container)
```

> Note:
>
> `unmountComponentAtNode` has been replaced with `root.unmount()` in React 18. See [createRoot](https://devdocs.io/react/react-dom-client#createroot) for more info.

Remove a mounted React component from the DOM and clean up its event handlers and state. If no component was mounted in the container, calling this function does nothing. Returns `true` if a component was unmounted and `false` if there was no component to unmount.

# createRoot()

#### `createRoot()` <a href="#createroot" id="createroot"></a>

```
createRoot(container[, options]);
```

Create a React root for the supplied `container` and return the root. The root can be used to render a React element into the DOM with `render`:

```
const root = createRoot(container);
root.render(element);
```

`createRoot` accepts two options:

* `onRecoverableError`: optional callback called when React automatically recovers from errors.
* `identifierPrefix`: optional prefix React uses for ids generated by `React.useId`. Useful to avoid conflicts when using multiple roots on the same page. Must be the same prefix used on the server.

The root can also be unmounted with `unmount`:

```
root.unmount();
```

> Note:
>
> `createRoot()` controls the contents of the container node you pass in. Any existing DOM elements inside are replaced when render is called. Later calls use React’s DOM diffing algorithm for efficient updates.
>
> `createRoot()` does not modify the container node (only modifies the children of the container). It may be possible to insert a component to an existing DOM node without overwriting the existing children.
>
> Using `createRoot()` to hydrate a server-rendered container is not supported. Use [`hydrateRoot()`](https://devdocs.io/react/react-dom-client#hydrateroot) instead.
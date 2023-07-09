# ⭐ render()

#### `render()` <a href="#render" id="render"></a>

```
render()
```

The `render()` method is the only required method in a class component.

When called, it should examine `this.props` and `this.state` and return one of the following types:

* **React elements.** Typically created via [JSX](https://devdocs.io/react/introducing-jsx). For example, `<div />` and `<MyComponent />` are React elements that instruct React to render a DOM node, or another user-defined component, respectively.
* **Arrays and fragments.** Let you return multiple elements from render. See the documentation on [fragments](https://devdocs.io/react/fragments) for more details.
* **Portals**. Let you render children into a different DOM subtree. See the documentation on [portals](https://devdocs.io/react/portals) for more details.
* **String and numbers.** These are rendered as text nodes in the DOM.
* **Booleans or `null`**. Render nothing. (Mostly exists to support `return test && <Child />` pattern, where `test` is boolean.)

The `render()` function should be pure, meaning that it does not modify component state, it returns the same result each time it’s invoked, and it does not directly interact with the browser.

If you need to interact with the browser, perform your work in `componentDidMount()` or the other lifecycle methods instead. Keeping `render()` pure makes components easier to think about.

> Note
>
> `render()` will not be invoked if [`shouldComponentUpdate()`](https://devdocs.io/react/react-component#shouldcomponentupdate) returns false.

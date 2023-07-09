# constructor()

#### `constructor()` <a href="#constructor" id="constructor"></a>

```
constructor(props)
```

**If you don’t initialize state and you don’t bind methods, you don’t need to implement a constructor for your React component.**

The constructor for a React component is called before it is mounted. When implementing the constructor for a `React.Component` subclass, you should call `super(props)` before any other statement. Otherwise, `this.props` will be undefined in the constructor, which can lead to bugs.

Typically, in React constructors are only used for two purposes:

* Initializing [local state](https://devdocs.io/react/state-and-lifecycle) by assigning an object to `this.state`.
* Binding [event handler](https://devdocs.io/react/handling-events) methods to an instance.

You **should not call `setState()`** in the `constructor()`. Instead, if your component needs to use local state, **assign the initial state to `this.state`** directly in the constructor:

```
constructor(props) {
  super(props);
  // Don't call this.setState() here!
  this.state = { counter: 0 };
  this.handleClick = this.handleClick.bind(this);
}
```

Constructor is the only place where you should assign `this.state` directly. In all other methods, you need to use `this.setState()` instead.

Avoid introducing any side-effects or subscriptions in the constructor. For those use cases, use `componentDidMount()` instead.

> Note
>
> **Avoid copying props into state! This is a common mistake:**
>
> ```
> constructor(props) {
>  super(props);
>  // Don't do this!
>  this.state = { color: props.color };
> }
> ```
>
> The problem is that it’s both unnecessary (you can use `this.props.color` directly instead), and creates bugs (updates to the `color` prop won’t be reflected in the state).
>
> **Only use this pattern if you intentionally want to ignore prop updates.** In that case, it makes sense to rename the prop to be called `initialColor` or `defaultColor`. You can then force a component to “reset” its internal state by [changing its `key`](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html#recommendation-fully-uncontrolled-component-with-a-key) when necessary.
>
> Read our [blog post on avoiding derived state](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html) to learn about what to do if you think you need some state to depend on the props.

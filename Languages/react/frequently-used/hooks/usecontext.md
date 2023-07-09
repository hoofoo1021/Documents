# useContext

#### `useContext` <a href="#usecontext" id="usecontext"></a>

```
const value = useContext(MyContext);
```

Accepts a context object (the value returned from `React.createContext`) and returns the current context value for that context. The current context value is determined by the `value` prop of the nearest `<MyContext.Provider>` above the calling component in the tree.

When the nearest `<MyContext.Provider>` above the component updates, this Hook will trigger a rerender with the latest context `value` passed to that `MyContext` provider. Even if an ancestor uses [`React.memo`](https://devdocs.io/react/react-api#reactmemo) or [`shouldComponentUpdate`](https://devdocs.io/react/react-component#shouldcomponentupdate), a rerender will still happen starting at the component itself using `useContext`.

Don’t forget that the argument to `useContext` must be the _context object itself_:

* **Correct:** `useContext(MyContext)`
* **Incorrect:** `useContext(MyContext.Consumer)`
* **Incorrect:** `useContext(MyContext.Provider)`

A component calling `useContext` will always re-render when the context value changes. If re-rendering the component is expensive, you can [optimize it by using memoization](https://github.com/facebook/react/issues/15156#issuecomment-474590693).

> Tip
>
> If you’re familiar with the context API before Hooks, `useContext(MyContext)` is equivalent to `static contextType = MyContext` in a class, or to `<MyContext.Consumer>`.
>
> `useContext(MyContext)` only lets you _read_ the context and subscribe to its changes. You still need a `<MyContext.Provider>` above in the tree to _provide_ the value for this context.

**Putting it together with Context.Provider**

```
const themes = {
  light: {
    foreground: "#000000",
    background: "#eeeeee"
  },
  dark: {
    foreground: "#ffffff",
    background: "#222222"
  }
};

const ThemeContext = React.createContext(themes.light);

function App() {
  return (
    <ThemeContext.Provider value={themes.dark}>
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar(props) {
  return (
    <div>
      <ThemedButton />
    </div>
  );
}

function ThemedButton() {
  const theme = useContext(ThemeContext);

  return (
    <button style={{ background: theme.background, color: theme.foreground }}>
      I am styled by theme context!
    </button>
  );
}
```

This example is modified for hooks from a previous example in the [Context Advanced Guide](https://devdocs.io/react/context), where you can find more information about when and how to use Context.

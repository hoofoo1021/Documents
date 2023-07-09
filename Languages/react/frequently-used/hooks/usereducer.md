# useReducer

#### `useReducer` <a href="#usereducer" id="usereducer"></a>

```
const [state, dispatch] = useReducer(reducer, initialArg, init);
```

An alternative to [`useState`](https://devdocs.io/react/hooks-reference#usestate). Accepts a reducer of type `(state, action) => newState`, and returns the current state paired with a `dispatch` method. (If you’re familiar with Redux, you already know how this works.)

`useReducer` is usually preferable to `useState` when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one. `useReducer` also lets you optimize performance for components that trigger deep updates because [you can pass `dispatch` down instead of callbacks](https://devdocs.io/react/hooks-faq#how-to-avoid-passing-callbacks-down).

Here’s the counter example from the [`useState`](https://devdocs.io/react/hooks-reference#usestate) section, rewritten to use a reducer:

```
const initialState = {count: 0};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```

> Note
>
> React guarantees that `dispatch` function identity is stable and won’t change on re-renders. This is why it’s safe to omit from the `useEffect` or `useCallback` dependency list.

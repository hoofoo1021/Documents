# flushSync()

#### `flushSync()` <a href="#flushsync" id="flushsync"></a>

```
flushSync(callback)
```

Force React to flush any updates inside the provided callback synchronously. This ensures that the DOM is updated immediately.

```
// Force this state update to be synchronous.
flushSync(() => {
  setCount(count + 1);
});
// By this point, DOM is updated.
```

> Note:
>
> `flushSync` can significantly hurt performance. Use sparingly.
>
> `flushSync` may force pending Suspense boundaries to show their `fallback` state.
>
> `flushSync` may also run pending effects and synchronously apply any updates they contain before returning.
>
> `flushSync` may also flush updates outside the callback when necessary to flush the updates inside the callback. For example, if there are pending updates from a click, React may flush those before flushing the updates inside the callback.

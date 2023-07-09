# testRenderer.update()

#### `testRenderer.update()` <a href="#testrendererupdate" id="testrendererupdate"></a>

```
testRenderer.update(element)
```

Re-render the in-memory tree with a new root element. This simulates a React update at the root. If the new element has the same type and key as the previous element, the tree will be updated; otherwise, it will re-mount a new tree.

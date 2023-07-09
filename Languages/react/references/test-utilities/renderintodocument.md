# renderIntoDocument()

#### `renderIntoDocument()` <a href="#renderintodocument" id="renderintodocument"></a>

```
renderIntoDocument(element)
```

Render a React element into a detached DOM node in the document. **This function requires a DOM.** It is effectively equivalent to:

```
const domContainer = document.createElement('div');
ReactDOM.createRoot(domContainer).render(element);
```

> Note:
>
> You will need to have `window`, `window.document` and `window.document.createElement` globally available **before** you import `React`. Otherwise React will think it can’t access the DOM and methods like `setState` won’t work.

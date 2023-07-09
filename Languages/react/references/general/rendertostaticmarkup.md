# renderToStaticMarkup()

#### `renderToStaticMarkup()` <a href="#rendertostaticmarkup" id="rendertostaticmarkup"></a>

```
ReactDOMServer.renderToStaticMarkup(element)
```

Similar to [`renderToString`](https://devdocs.io/react/react-dom-server#rendertostring), except this doesn’t create extra DOM attributes that React uses internally, such as `data-reactroot`. This is useful if you want to use React as a simple static page generator, as stripping away the extra attributes can save some bytes.

If you plan to use React on the client to make the markup interactive, do not use this method. Instead, use [`renderToString`](https://devdocs.io/react/react-dom-server#rendertostring) on the server and [`ReactDOM.hydrateRoot()`](https://devdocs.io/react/react-dom-client#hydrateroot) on the client.

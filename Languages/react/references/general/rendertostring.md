# 🌵 renderToString()

#### `renderToString()` <a href="#rendertostring" id="rendertostring"></a>

```
ReactDOMServer.renderToString(element)
```

Render a React element to its initial HTML. React will return an HTML string. You can use this method to generate HTML on the server and send the markup down on the initial request for faster page loads and to allow search engines to crawl your pages for SEO purposes.

If you call [`ReactDOM.hydrateRoot()`](https://devdocs.io/react/react-dom-client#hydrateroot) on a node that already has this server-rendered markup, React will preserve it and only attach event handlers, allowing you to have a very performant first-load experience.

> Note
>
> This API has limited Suspense support and does not support streaming.
>
> On the server, it is recommended to use either [`renderToPipeableStream`](https://devdocs.io/react/react-dom-server#rendertopipeablestream) (for Node.js) or [`renderToReadableStream`](https://devdocs.io/react/react-dom-server#rendertoreadablestream) (for Web Streams) instead.

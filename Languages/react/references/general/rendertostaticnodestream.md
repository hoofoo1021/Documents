# 🍕 renderToStaticNodeStream()

#### `renderToStaticNodeStream()` <a href="#rendertostaticnodestream" id="rendertostaticnodestream"></a>

```
ReactDOMServer.renderToStaticNodeStream(element)
```

Similar to [`renderToNodeStream`](https://devdocs.io/react/react-dom-server#rendertonodestream), except this doesn’t create extra DOM attributes that React uses internally, such as `data-reactroot`. This is useful if you want to use React as a simple static page generator, as stripping away the extra attributes can save some bytes.

The HTML output by this stream is exactly equal to what [`ReactDOMServer.renderToStaticMarkup`](https://devdocs.io/react/react-dom-server#rendertostaticmarkup) would return.

If you plan to use React on the client to make the markup interactive, do not use this method. Instead, use [`renderToNodeStream`](https://devdocs.io/react/react-dom-server#rendertonodestream) on the server and [`ReactDOM.hydrateRoot()`](https://devdocs.io/react/react-dom-client#hydrateroot) on the client.

> Note:
>
> Server-only. This API is not available in the browser.
>
> The stream returned from this method will return a byte stream encoded in utf-8. If you need a stream in another encoding, take a look at a project like [iconv-lite](https://www.npmjs.com/package/iconv-lite), which provides transform streams for transcoding text.

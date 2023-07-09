# CDN Links

Both React and ReactDOM are available over a CDN.

```
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
```

The versions above are only meant for development, and are not suitable for production. Minified and optimized production versions of React are available at:

```
<script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
```

To load a specific version of `react` and `react-dom`, replace `18` with the version number.

#### Why the `crossorigin` Attribute?

If you serve React from a CDN, we recommend to keep the [`crossorigin`](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS\_settings\_attributes) attribute set:

```
<script crossorigin src="..."></script>
```

We also recommend to verify that the CDN you are using sets the `Access-Control-Allow-Origin: *` HTTP header:



This enables a better error handling experience in React 16 and later.

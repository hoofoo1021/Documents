# TestRenderer.create()

#### `TestRenderer.create()` <a href="#testrenderercreate" id="testrenderercreate"></a>

```
TestRenderer.create(element, options);
```

Create a `TestRenderer` instance with the passed React element. It doesn’t use the real DOM, but it still fully renders the component tree into memory so you can make assertions about it. Returns a [TestRenderer instance](https://devdocs.io/react/test-renderer#testrenderer-instance).

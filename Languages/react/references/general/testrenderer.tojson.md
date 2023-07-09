# testRenderer.toJSON()

#### `testRenderer.toJSON()` <a href="#testrenderertojson" id="testrenderertojson"></a>

```
testRenderer.toJSON()
```

Return an object representing the rendered tree. This tree only contains the platform-specific nodes like `<div>` or `<View>` and their props, but doesn’t contain any user-written components. This is handy for [snapshot testing](https://facebook.github.io/jest/docs/en/snapshot-testing.html#snapshot-testing-with-jest).

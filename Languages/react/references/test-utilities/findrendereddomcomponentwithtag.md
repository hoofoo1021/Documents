# findRenderedDOMComponentWithTag()

#### `findRenderedDOMComponentWithTag()` <a href="#findrendereddomcomponentwithtag" id="findrendereddomcomponentwithtag"></a>

```
findRenderedDOMComponentWithTag(
  tree,
  tagName
)
```

Like [`scryRenderedDOMComponentsWithTag()`](https://devdocs.io/react/test-utils#scryrendereddomcomponentswithtag) but expects there to be one result, and returns that one result, or throws exception if there is any other number of matches besides one.

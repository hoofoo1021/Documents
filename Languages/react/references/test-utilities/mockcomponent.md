# mockComponent()

#### `mockComponent()` <a href="#mockcomponent" id="mockcomponent"></a>

```
mockComponent(
  componentClass,
  [mockTagName]
)
```

Pass a mocked component module to this method to augment it with useful methods that allow it to be used as a dummy React component. Instead of rendering as usual, the component will become a simple `<div>` (or other tag if `mockTagName` is provided) containing any provided children.

> Note:
>
> `mockComponent()` is a legacy API. We recommend using [`jest.mock()`](https://jestjs.io/docs/tutorial-react-native#mock-native-modules-using-jestmock) instead.

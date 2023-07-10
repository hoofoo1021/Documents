# 🍕 Refs

React supports a special attribute that you can attach to any component. The `ref` attribute can be an object created by `React.createRef()` function or a callback function, or a string (in legacy API). When the `ref` attribute is a callback function, the function receives the underlying DOM element or class instance (depending on the type of element) as its argument. This allows you to have direct access to the DOM element or component instance.

Use refs sparingly. If you find yourself often using refs to “make things happen” in your app, consider getting more familiar with top-down data flow.

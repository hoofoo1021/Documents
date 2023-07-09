# 🌵 state

#### `state` <a href="#state" id="state"></a>

The state contains data specific to this component that may change over time. The state is user-defined, and it should be a plain JavaScript object.

If some value isn’t used for rendering or data flow (for example, a timer ID), you don’t have to put it in the state. Such values can be defined as fields on the component instance.

See [State and Lifecycle](https://devdocs.io/react/state-and-lifecycle) for more information about the state.

Never mutate `this.state` directly, as calling `setState()` afterwards may replace the mutation you made. Treat `this.state` as if it were immutable.

Is this page useful?

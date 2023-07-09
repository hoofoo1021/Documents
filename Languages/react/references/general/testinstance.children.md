# testInstance.children

#### `testInstance.children` <a href="#testinstancechildren" id="testinstancechildren"></a>

```
testInstance.children
```

The children test instances of this test instance.

### Ideas <a href="#ideas" id="ideas"></a>

You can pass `createNodeMock` function to `TestRenderer.create` as the option, which allows for custom mock refs. `createNodeMock` accepts the current element and should return a mock ref object. This is useful when you test a component that relies on refs.

```
import TestRenderer from 'react-test-renderer';

class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.input = null;
  }
  componentDidMount() {
    this.input.focus();
  }
  render() {
    return <input type="text" ref={el => this.input = el} />
  }
}

let focused = false;
TestRenderer.create(
  <MyComponent />,
  {
    createNodeMock: (element) => {
      if (element.type === 'input') {
        // mock a focus function
        return {
          focus: () => {
            focused = true;
          }
        };
      }
      return null;
    }
  }
);
expect(focused).toBe(true);
```

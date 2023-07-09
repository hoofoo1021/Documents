# TestRenderer.act()

#### `TestRenderer.act()` <a href="#testrendereract" id="testrendereract"></a>

```
TestRenderer.act(callback);
```

Similar to the [`act()` helper from `react-dom/test-utils`](https://devdocs.io/react/test-utils#act), `TestRenderer.act` prepares a component for assertions. Use this version of `act()` to wrap calls to `TestRenderer.create` and `testRenderer.update`.

```
import {create, act} from 'react-test-renderer';
import App from './app.js'; // The component being tested

// render the component
let root; 
act(() => {
  root = create(<App value={1}/>)
});

// make assertions on root 
expect(root.toJSON()).toMatchSnapshot();

// update with some different props
act(() => {
  root.update(<App value={2}/>);
})

// make assertions on root 
expect(root.toJSON()).toMatchSnapshot();
```

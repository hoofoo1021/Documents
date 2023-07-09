# defaultProp

#### `defaultProps` <a href="#defaultprops" id="defaultprops"></a>

`defaultProps` can be defined as a property on the component class itself, to set the default props for the class. This is used for `undefined` props, but not for `null` props. For example:

```
class CustomButton extends React.Component {
  // ...
}

CustomButton.defaultProps = {
  color: 'blue'
};
```

If `props.color` is not provided, it will be set by default to `'blue'`:

```
  render() {
    return <CustomButton /> ; // props.color will be set to blue
  }
```

If `props.color` is set to `null`, it will remain `null`:

```
  render() {
    return <CustomButton color={null} /> ; // props.color will remain null
  }
```

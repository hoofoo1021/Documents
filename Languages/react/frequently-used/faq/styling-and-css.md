# 🌵 Styling and CSS

#### How do I add CSS classes to components?

Pass a string as the `className` prop:

```
render() {
  return <span className="menu navigation-menu">Menu</span>
}
```

It is common for CSS classes to depend on the component props or state:

```
render() {
  let className = 'menu';
  if (this.props.isActive) {
    className += ' menu-active';
  }
  return <span className={className}>Menu</span>
}
```

> Tip
>
> If you often find yourself writing code like this, [classnames](https://www.npmjs.com/package/classnames#usage-with-reactjs) package can simplify it.

#### Can I use inline styles?

Yes, see the docs on styling here.

#### Are inline styles bad?

CSS classes are generally better for performance than inline styles.

#### What is CSS-in-JS?

“CSS-in-JS” refers to a pattern where CSS is composed using JavaScript instead of defined in external files.

_Note that this functionality is not a part of React, but provided by third-party libraries._ React does not have an opinion about how styles are defined; if in doubt, a good starting point is to define your styles in a separate `*.css` file as usual and refer to them using `className`.

#### Can I do animations in React?

React can be used to power animations. See [React Transition Group](https://reactcommunity.org/react-transition-group/), [React Motion](https://github.com/chenglou/react-motion), [React Spring](https://github.com/react-spring/react-spring), or [Framer Motion](https://framer.com/motion), for example.

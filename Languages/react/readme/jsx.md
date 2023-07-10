# JSX

JSX is a syntax extension to JavaScript. It is similar to a template language, but it has full power of JavaScript. JSX gets compiled to `React.createElement()` calls which return plain JavaScript objects called “React elements”. To get a basic introduction to JSX see the docs here and find a more in-depth tutorial on JSX here.

React DOM uses camelCase property naming convention instead of HTML attribute names. For example, `tabindex` becomes `tabIndex` in JSX. The attribute `class` is also written as `className` since `class` is a reserved word in JavaScript:

```
<h1 className="hello">My name is Clementine!</h1>
```

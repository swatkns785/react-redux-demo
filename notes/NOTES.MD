ways to create react components

-ES5 createClass
```js
var HelloWorld = React.createClass({
  render: function () {
    return (
      <h1>Hello World</h1>
    );
  }
});
```
-ES6 class
```js
class Contacts extends React.Component {
  constructor(props) {
    super(props);
    this.handleClick = this.handleClick.bind(this);
  }
}
```
--No autobind
--PropTypes declared separately
--Default props declared separately
--Set initial state in constructor

-ES5 stateless function
```js
var HelloWorld = function(props) {
  return (
    <h1>Hello World</h1>
  );
};
```
-ES6 stateless function
```js
const HelloWorld = (props) => {
  return (
    <h1>Hello World</h1>
  );
};
```

When to use stateless functional components
-see screenshot

###Container vs Presentation Components
####Container
-Little to no markup
-Pass data and actions down to pres components
-Knows about Redux
-Often stateful

####Presentation
-Nearly all markup
-Receive data and actions via props
-Doesnt know about Redux
-Typically functional components

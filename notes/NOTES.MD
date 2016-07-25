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


##Actions, Stores, and Reducers in Redux

###Actions

```js
rateCourse(rating) {
  return { type: RATE_COURSE, rating: rating }
}
```

###Immutability
**TO CHANGE STATE, RETURN A NEW OBJECT**

Why?
-Clarity, state is changed in a reducer
-Performance
-Improved debugging experience

`Object.assign` or Spread operator in ES6

###Reducers
```js
function myReducer(state, action) {
  // Return new state based on action passed
}

function myReducer(state, action) {
  switch (action.type) {
    case 'INCREMENT_COUNTER':
      return (Object.assign(
        {},
        state,
        {counter: state.counter + 1}
      ));
  }
}
```

####Forbidden in reducers
-Mutate arguments
-Perform side effects
-Call non-pure functions


##React-Redux Connection
```js
connect(mapStateToProps, mapDispatchToProps)
```

mapStateToProps === What state should I expose to props?
```js
function mapStateToProps(state) {
  return {
    appState: state
  };
}
```

mapDispatchToProps === what actions do I want on props?
```js
function mapDispatchToProps(dispatch) {
  return {
    actions: bindActionCreators(actions, dispatch)
  };
}
```

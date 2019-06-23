---
title: Map Dispatch to Props
---
## Map Dispatch to Props

`mapDispatchToProps()` needs to be defined as a function that takes `dispatch` as an argument. The `mapDispatchToProps()` function needs to `return` an object with one paramenter, in this case, the parameter name will be `submitNewMessage`:

```
const mapDispatchToProps = dispatch => {
  return {
    submitNewMessage: }
  }
}
```

Now the value of the `submitNewMessage` needs to be set to the dispatch function, which itself needs to take the actionCreator data payload – defined at the top of this challenge's code as `message` – as an argument. This can be be written as an anonymous function which invokes the previously defined `addMessage()` actionCreator, passing it the `message` argument (which varies slightly in style from the example given in the challenge description):

```
message => { dispatch(addMessage(message)) }
```

## Solution
The full `mapDispatchToProps()` function ends up looking like:

```
const mapDispatchToProps = dispatch => {
  return {
    submitNewMessage: message => { dispatch(addMessage(message)) }
  }
}
```

This grants access to the action creator via a given React component's props.

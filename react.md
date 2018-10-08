# React Notes

### Component

### componentWillMount() - Immediately before initial rendering

Your component is in default position at this point. Almost everything should be taken care of by the rest of your component code, without the complication of an additional lifecycle method.

The exception is any setup that can only be done at runtime — namely, connecting to external API’s. For example, if you use Firebase for your app, you’ll need to get that set up as your app is first mounting.

But the key is that such configuration should be done at the highest level component of your app (the root component). That means 99% of your components should probably not use componentWillMount.


### componentDidMount() - Immediately after initial rendering

ComponentDidMount is also where you can do all the fun things you couldn’t do when there was no component to play with. Here are some examples:
* draw on a canvas element that you just rendered
initialize a masonry grid layout from a collection of elements
* add event listeners
* Basically, here you want to do all the setup you couldn’t do without a DOM, and start getting all the data you need.

Most Common Use Case: Starting AJAX calls to load in data for your component.

Can call setState: Yes.

### componentWillReceiveProps() - When component receives new props

Our component was doing just fine, when all of a sudden a stream of new props arrive to mess things up.

Perhaps some data that was loaded in by a parent component’s componentDidMount finally arrived, and is being passed down.

Before our component does anything with the new props, componentWillReceiveProps is called, with the next props as the argument.

Most Common Use Case: Acting on particular prop changes to trigger state transitions.

Can call setState: Yes.


### componentWillUpdate() - Before rendering, but after receiving new props or state

### componentDidUpdate() - After component's updates are flushed to the DOM.

### componentWillUnmount() - Immediately before removing component from DOM

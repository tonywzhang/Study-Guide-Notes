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

If you were using shouldComponentUpdate AND needed to do something when props change, componentWillUpdate makes sense. But it’s probably not going to give you a whole lot of additional utility.

Most Common Use Case: Used instead of componentWillReceiveProps on a component that also has shouldComponentUpdate (but no access to previous props).

Can call setState: No.

### componentDidUpdate() - After component's updates are flushed to the DOM.

If our component is receiving more props than those relevant to our canvas, we don’t want to waste time redrawing the canvas every time it updates.

That doesn’t mean componentDidUpdate isn’t useful. To go back to our masonry layout example, we want to rearrange the grid after the DOM itself updates — so we use componentDidUpdate to do so.

Most Common Use Case: Updating the DOM in response to prop or state changes.

Can call setState: Yes.

### componentWillUnmount() - Immediately before removing component from DOM

Your component is going to go away. Maybe forever. It’s very sad.

Before it goes, it asks if you have any last-minute requests.

Here you can cancel any outgoing network requests, or remove all event listeners associated with the component.

Basically, clean up anything to do that solely involves the component in question — when it’s gone, it should be completely gone.

Most Common Use Case: Cleaning up any leftover debris from your component.

Can call setState: No.


- An event is an action that occurs on your app
- the event process:
	- one or more functions can be registered as event listeners to handle an event
		- `source.addEventListener(eventType, listener, [options]);`
	- When an event occurs, the source object (aka the emitter) will raise (aka fire) the event
	- All registered listener functions will be called
	- A listener can be removed if not wanted anymore
		- `source.removeEventListener(eventType, listener);`

#### Common DOM events:
- Mouse
	- `click, dblclick, mousemove, mouseleave, mouseenter, mousedown, mouseup, mousewheel`
- Keyboard
	- `keydown, keyup`
- Form & Form elements
	- `reset, change, submit, focus, blur`
- Document & other
	- `touch*`, `pointer*`, `drag*`, `DOMContentLoaded`, `animation*`, `load`


### DOM Event Interface
- DOM event handlers are called with an `event` object as parameter
	- Based on the `Event` interface
	- But is usually extended with more properties and/or methods
- `Event.target` refers to the element where the event occurred
- ![img](<images/Pasted image 20250128211056.png>)


### `DOMContentLoaded` and `load`

- `document.DOMContentLoaded`
	- Fires when the browser finished creating the DOM
	- Waits until deferred scripts are downloaded and executed
- `window.load`
	- Fires when page and all resources have been loaded
![img](<images/Pasted image 20250128211402.png>)



# Preventing Default Behavior
- Some user actions result in default responses
	- Typing on a text field causes characters to appear inside of the text field
	- Pressing the ENTER key on a form causes the form to be submitted
- We can stop these default behaviors
	- `Event.preventDefault();`
- ![img](<images/Pasted image 20250128211536.png>)


### Keyboard Events
- `keydown`, fired when a key is pressed or held
- `keyup`, fired when a key is released
- The event object contains information about which key triggered the event and the state of modifier keys
	- `KeyboardEvent.key`: string representation of the key pressed (e.g., "X")
	- `KeyboardEvent.code`: string with code value (e.g., "KeyX") 
	- `KeyboardEvent.ctrlKey`: true if CTRL key was active 
	- `KeyboardEvent.shiftKey`: true if SHIFT key was active 
	- `KeyboardEvent.altKey`: true if ALT key was active 




### Event Bubbling & Capture

- JS propagates events; they have a capturing phase and a bubbling phase
- If you have event listeners for nested elements, JS triggers events from child to parent
- `capture` → boolean that reverses the order in which events are triggered (only works for nested event listeners) // not quite, experiment with this
- `e.stopPropogation()` → stops events from propagating further
- `e.cancelBubble` → boolean value that 

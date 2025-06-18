((i
- Many uses of javaScript involve asynchronous processes
- we use **callbacks** to receive asynchronous notifications
	- our callback is a function

## setTimeout
- executes a function after a certain amount of time elapsed
- `setTimeout(function: you want to execute, int: how far into the future do you want to execute the funciton)`

## Promise
- an object that represents a future value (success or error)
- A promise is
	- pending while the asynchronous process is executing
	- can resolve when the process completes successfully
	- can reject when the process fails
- An asynch process can return a promise object instead of using a callback
(![img](<images/Pasted image 20250126215623.png>)

## Using Promises
(![img](<images/Pasted image 20250126215837.png>)


# Using JavaScript
- External scripts
	- use `<script src="path/to/script.js"></script>`
- Embedded script
	- `<script> ... </script>`

## JS in the Browser
- Global (root) object: `window`
	- all global functions attach to it
	- BOM: browser object model (API to interact with browser)
	- DOM: document object model
(![img](<images/Pasted image 20250126220159.png>)

## JS Console and Dev Tools

- The javascript `console` runs in the same context as code on the page
- Shows any errors, warnings, logs
- Use it programmatically via global console object


## JavaScript execution
- By default, asap
	- Embedded scripts when parsed by the browser
	- external scripts when the browser finishes downloading them
	- This is true even if other things in the page are still loading
- Some `<script>` attributes can change this behavior in external scripts:
	- `defer`
	- `async`
(![img](<images/Pasted image 20250126220729.png>)

# The DOM
- Document object model
- It is the representation of all html elements from a file as an object
(![img](<images/Pasted image 20250126221405.png>)
- The DOM is a Tree of `Node`s
	- the root of the DOM is `document`
	- Not all `Node`s are HTML `Element`s
		- attributes, comments, text, etc.
	- `Element.tagName` - tells you the name of the tag of the html element

## Traversing the DOM
(![img](<images/Pasted image 20250126221751.png>)

## Querying the DOM
(![img](<images/Pasted image 20250126222039.png>)
- `Element.querySelector("#wow")` finds first element that has the id wow

## Manipulating the DOM
(![img](<images/Pasted image 20250126222345.png>)





a.

 

b.

`document.querySelectorAll(".container .message");`  

c.

`document.querySelectorAll(".message");`  

d.

`document.querySelectorAll("div .message");`  

e.



f.

`document.querySelectorAll(".container > div.message");`  

g.

`document.querySelectorAll(".container > div.message");`  

h.



i.

`document.querySelector(".container").querySelectorAll(".message");`  

j.

`document.querySelectorAll(".container > .message");`








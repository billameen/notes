# Dynamic Content

## Goal
- We want to have a dedicated page for each thing
	- Ex: A website that contains schedule information for each ncsu student
- We don't want to create a separate HTML file for each thing
	- the pages look very similar, but are different at some places

## Two Approaches
- Client-side Rendering (CSR)
	- Partial HTML provided by the server
	- Content is added via JavaScript

	- Only partial HTML is provided by server
	- that template HTML is then populated by the client
- Server-side Rendering (SSR)
	- Full HTML provided by the server

	- Server composes entire HTML file

- These approaches can be combined

# Client-side Rendering (CSR)

- Server only provides a skeleton HTML
- Server provides minimal HTML, like header, footer, common navigation, GUI elemnts etc.
- Reduces load on the server
- Javascript is used to retrieve and repopulate content on the page
	- ie. we can use GET params to determine what to render
- This is the foundation behind Single Page Applications (SPAs)
	- CSR should NOT be confused with SPA
	- All SPAs are CSR, but not all CSR are SPA

## Retrieving Query String Parameters via JavaScript

- We can inspect the URL of the current page via `window.location` or `document.location`
	- This will basically be a location object
- From this `Location` object you can read the protocol, host, hostname, port, pathname, search, hash, etc. (basically every element of the URL)
	- https://developer.mozilla.org/en-US/docs/Web/API/Location
- The query strring (GET parameters) are available via the `search` property of location
	- `window.location.search`

![img](<images/Pasted image 20250218223628.png>)

![img](<images/Pasted image 20250218223923.png>)

![img](<images/Pasted image 20250218224129.png>)


# Server-side Rendering

- Less code and stuff to worry about on the client side
	- It doesn't even need to know where the data is coming from, or that the pages are dynamic at all.
	- It just receives HTML and displays it.
![img](<images/Pasted image 20250218224601.png>)

![img](<images/Pasted image 20250218224751.png>)

![img](<images/Pasted image 20250218225025.png>)




## Positioning and Flow
- `static`: 
	- the default positioning
- `relative`: 
	- defines anchor point (typically parent element)
	- Element can be top/right/bottom of parent
- `absolute`:
	- position is dependent on nearest ancestor, else its dependent on viewport
	- ancestor is usually already positioned, so it's relies on that
- `fixed`:
	- position is dependent on viewport, so you can put things anywhere on the screen and have it stay there throughout the entire site
	- other content is rendered underneath the fixed element, and no amount of scrolling will change that
- `sticky`:
	- Basically a fixed element, but if you scroll, that element will get stuck at the top of the window, kinda like the navbar of fancy websites
	- You need to specify a direction for it to work properly, like `top: 0;` or `bottom: 0;`
 ![[Pasted image 20250114215612.png]]

- Floats
	- Allows content to wrap around an element
	- can be left or right
		- `float: left;` or `float: right;`
	- Can stop this behavior using:
		- `clear: left;`, `clear: right;`, or `clear: both;`
## Element Display Types

Two kinds: inner and outer
- Outer display type: how element boxes relate to other boxes around them
- Inner display type: how elements nested inside will be rendered
- Set with `display` CSS property
![[Pasted image 20250114220410.png]]
![[Pasted image 20250114220457.png]]
![[Pasted image 20250114220604.png]]

## CSS Flexbox

- `display: flex;` or `display: inline-flex;`
	- Outer display type
	- Designates an element as a flex container
	- Makes all its children flex items (inner display type)
![[Pasted image 20250114220911.png]]

### Flex Direction
- Specifies direction/orientation of the main axis. This means you can change the main start and main end however you want
- `flex-direction:`
	- `row`: default behavior, flex items rendered left to right
	- `row-reverse`: flex items rendered right to left
	- `column`: flex items rendered north to south
	- `column-reverse`: flex items rendered south to north

![[Pasted image 20250114221348.png]]
- `flex-wrap`:
	- `wrap;`wraps flex items onto multiple lines if there isn't enough space
	- `nowrap;`default value

## CSS Grid

- Table layout
- use `display: grid;` for block type outer display 
- use `display: inline-grid;`for inline type outer display
- Designates an element as a grid container, and all its inner components (the rows and columns) as grid items
![[Pasted image 20250114222026.png]]

### Grid Template
- Defines the structure of the grid: how many rows and columns
- You can define how much space, relative to each other, that each row and column should take.
	- uses a special `fr`(fraction) unit
	- The following css and html define how to divide up a table into the image above. We still haven't defined how each box will fit into the table though, just the dimensions. It just shows that each row and column is of equal size![[Pasted image 20250114222618.png]]


![[Pasted image 20250114223245.png]]
- If you see the 1 / 4 in the grid-column section, thats just saying "span from position 1 to 4"
- pay close attention to the numbers on the table
#### Alternative:
![[Pasted image 20250114223821.png]]

Useful websites:
- flexbox.tech
- https://loading.io/flexbox#editor
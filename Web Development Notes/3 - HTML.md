
## URL
- Identifies a resource, its location, and how to get it
- A type of Universal Resource Identifier (URI)
- Has multiple parts:
	- Scheme
	- Authority
	- Path
	- Query
	- Fragment
![[Pasted image 20250107232115.png]]

- protocol: https://
- host: www.ncsu.edu
- resource: /about/

## Website vs Web Application
| Website                                           | WebApplication                                                    |
| ------------------------------------------------- | ----------------------------------------------------------------- |
| HTML + CSS + JS                                   | HTML + CSS + JS                                                   |
| Tend to be static                                 | Dynamic Content                                                   |
| Little to no user input                           | Interactive: user input expected                                  |
| main purpose is to allow users to consume content | Generally, meant for users to "do" something-- its more tool-like |
In reality, there is a blurry line between the two. Don't try to classify things into one or the other, use it as a way to think about the different uses.

## Web Resources: Separation of Concerns
- HTML -> Content
- CSS -> Presentation
- JS -> Behavior


# HTML
- Hypertext Markup Language
- Describes structure and content of page
- Structure is provided by annotating content with **tags
- Tags are case-insensitive and whitespace is ignored

What's Hypertext?
- text with links to other text aka **hyperlinks**

### Basic HTML Elements
- Headers: \<h1>\<h2>\<h3>
- Paragraph: \<p>
- Horizontal Rule: \<hr>
- Link/Anchor: \<a>
- Lists:
	- Unordered (bulleted): \<ul>
	- Ordered (numbered): \<ol>
	- List item (ordered or unordered): \<li>
- Image: \<img>
- Line break: \<br>
- Block divider: \<div>
- Text Span: \<span>
- Comments: \<!-- ... any number of lines... -->
### Element Flow
- Inline elements: flow left to right until no space
	- Ex: \<span>
- Block element: generally start on a new line
	- Ex: \<div>
- **Do not place blocks inside of inline elements**

### Element Attributes
- Additional information (metadata) for an element
	- Added inside opening tag
	- Format: `name="value"`
- for tags like \<img>

### Global Attributes
- Attributes supported by all HTML elements
- Ex: id, class, style

### Semantic HTML Elements
- Elements that ascribe meaning to their content
- Removes cluttering of global attributes

### HTML Entities
- Allows us to specify characters that would be interpreted as markup, kinda like an escape sequence
- formated as &--;
- Ex: <p> I have some &lt;br&gt;eaking news.\</p>
- There are named (common) vs unicode ones:
	- common: &nbsp;
	- unicode: &#160;

![[Pasted image 20250107235055.png]]



# HTML Element Attributes in Detail

### Images

`<img src="brick.jpg">

- `src`: required attribute
- `alt`: not required, but universally recommended
- `loading`:
	- only available if JS is enabled
	- `eager`
	- `lazy`
- `width` and `height`
	- CSS is preferred

### Inline frames (iframe)
Embeds another page into our page, creates another (nested) context

Content can be a URL or inline html.

Can use `width` `height` and `frameborder`, but CSS is preferred
Prevent Scrollbars with `scrolling="no"`
Ex. Whenever there is a map inside a webpage, it's usually using iframes

### Links/Anchors
\<a href="targetURL">text\</a>
- `targetURL` can be absolute or relative
- Anchor Links:
	- Can link to content in the same page
	- \<a href="#top">text\</a>
		- `#top` should be the `id` of some element in the page
- Other Attributes
	- `target`
		-  `_self` - opens link in same page
		- `_blank` - opens in new window/tab
		- `parent` - open in same iframe
		- `_top` topmost ancestor frame (if any)
	- `title`: describes the purpose of the link, useful for screen readers
	- `download`: allows user to download the file

### Tables
\<table>
\<tr>
	\<td>\</td>
\<tr>

tr -> table row
td -> table data

- Span rows or columns via attribute
	- colspan='#'
	- rowspan='#'

- Can have header, body and footer rows
\<thead>
\<tbody>
\<tfoot>


### Summary

![[Pasted image 20250108000809.png]]


### Forms
![[Pasted image 20250108000856.png]]


HTML Validation Service:
https://validator.w3.org/

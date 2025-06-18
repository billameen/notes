- HTML has default values that are not universal for all browsers, CSS can fix that
- Cascading Stylesheets (CSS) defines presentation (visual appearance)

### Three Ways To Apply Styles
- External Stylesheets
	- `<link rel="stylesheet" href="/css/styles.css" />
- Embedded Stylesheets
	- `<style> // CSS Rules </style>`
- Inline Styles
	- `<p style="css_rule_1; css_rule_2;">Some text </p>`

![img](<images/Pasted image 20250112191116.png>)

## CSS Terminology

#### CSS Rules
- Modifies **values** on a set of **properties**
	- Ex: property → font, value → Calibri ---`font-family: Calibri;`
- **Selectors** specify which elements will modify their properties, basically a combination of rules - a ruleset
	- Inline: `p{font-size: 1.2em;}` → applies font-size 1.2em to all p tags
#### Colors
- Hex: \#RRGGBB
- Names/keywords: red, blue, orange, olivedrab, etc. (Theres a lot)
- RGB: `rgb(rv, gv, bv);`
	- 0%-100%
	- Integers 0-255
- RGBa: `rgba(rv, gv, bv, av);`
	- First 3 params same as rgb
	- Alpha is a float 0-1
#### Units
- **Absolute**
	- Most common: pt, px
	- others: cm, mm, in
- **Relative**
	- Depend on the definitions of something else
	- em (refers to the font size of the parent element), rem (font size of the root element), vh (viewport height, basically the height of your display), vw (viewport width), lh (line height)
#### Specificity
- If rules applied to an element conflict, the browser must decide which rules to apply
- Specificity is a weight on a CSS **declaration** (property + value)

## Box Model
- Specifies how to calculate the size of an element and space around it
	- Content, Padding, Border, Outline and Shadow: take no space, Margin
	- Default behavior: when you specify height and width, you only specify the content box size. If you specify additional properties, those size values will be **added** on to the content box size
![img](<images/Pasted image 20250112192920.png>)

## CSS Selectors
- Define the target of the CSS rules
### Most common selectors:
- Universal - applied to all tags
	- `{ color: red; }`
- Type/element - applied to all given tags
	- `p{ color: red; }`
- Class - applied to elements with a given class
	- `.alert { color: red; }`
- ID - applied to elements with a given id
	- `#id { color: red; }`
- Group - combine different selectors with commas
	- `h2, .alert, #navbar { color: red; }`
- Combined - basically an && operator
	- `p.alert { color: red; }` - applied to `<p>` and `.alert`
	- `.alert.success { color: red; }`- applied to `.success` and `.alert`
- Descendant - applied to elements based on their structure within the document
	- `header p { color: red; }` - applied to `<p>` INSIDE of `<header>`
- Child - more specific than descendant
	- `header > p { color: red; }` - applied to `<p>` DIRECTLY INSIDE of `<header>`
#### Attribute Selectors
![img](<images/Pasted image 20250112195639.png>)
#### Pseudo-class Selectors
- Applies to elements based on their state
	- `selector:pseudo-class { property: value; }`
- Examples: 
	- Structure - `:only-child`, `first-child`, `nth-child`, `:first-of-type`, `:only-of-type`, `:nth-of-type`, `:empty` 
	-  User Action: `:focus`, `:hover`, `:active`
	- Input (like a textbox): `:enabled`, `:read-only`, `:checked`, `:valid`, `:blank`, `:required`
#### Pseudo-element Selectors
- Applies to parts of an element
	- `selector::pseudo-element {property: value;}`
- Examples:
	- `::before`, `::after`, `::selection`, `::backdrop`, `::first-line`, `::marker`, `::first-letter`

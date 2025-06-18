
# Introduction to Responsive Design

- How to design things for mobile vs desktop browsers?
	- Create a different version for both mobile and desktop - tedious
	- Responsive Design

## Responsive Design
- Not a specific technology
- Set of practices used to render web pages differently to adapt to different device characteristics
	- Screen sizes
	- Resolution
	- Purpose (media type)
- Benefits:
	- Support good user eexperience on different devices and media
	- maintain a single codebase

# HTML Viewport Metadata
- Tell the browser the page is "mobile-optimized"
- `<meta name="viewport" content="width=device-width, initial-scalse=1.0">`
- This sets the width of the application to the width of the device and the initial zoom factor to 100%

- Always include it!
	- Your page will not be properly responsive otherwise
- Other useful properties
	- `minimum-scale`: minimum zoom level
	- `maximum-scale`: maximum zoom level
	- `user-scalable`: set to no to prevent zoom
- PWAs behave like native applications so zooming is typically disabled

## Relative Sizing
![[Pasted image 20250302200415.png]]

## em vs rem
![[Pasted image 20250302200425.png]]
- em looks at the font size of the parent element
- rem looks at the font size of the root element

# CSS Media Queries

![[Pasted image 20250302200638.png]]

## Media Query Rules

![[Pasted image 20250302200721.png]]
![[Pasted image 20250302200749.png]]


## Media Query Examples

![[Pasted image 20250302200923.png]]

## Using CSS Media Queries

![[Pasted image 20250302201122.png]]


# Responsive Images: Resolution Switching

![[Pasted image 20250302201350.png]]

![[Pasted image 20250302201732.png]]
![[Pasted image 20250302202053.png]]


![[Pasted image 20250302202321.png]]



# Responsive Images: Art Direction

![[Pasted image 20250302203358.png]]

![[Pasted image 20250302203501.png]]

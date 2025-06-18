C
# Client-side Form Validation

## Different Ways to Validate
- Client-side Validation
- 1. Broswer Built-in validation functionality
- 2.  Custom JavaScript Validation
	- both can work together

- Server-side validation
	- Remember that our front-end is a client to our back-end
	- There are many different kind of clients
	- What would happen if a different client is used?
	- Think of ways incorrect or malicious data will affect the behavior of our backend
	- Data received from a client should be validated and sanitized


![[Pasted image 20250216201951.png]]

![[Pasted image 20250216202121.png]]

![[Pasted image 20250216202242.png]]

![[Pasted image 20250216202344.png]]



# Server-side Form Validation

![[Pasted image 20250216202519.png]]

![[Pasted image 20250216202702.png]]

# JavaScript Modules

![[Pasted image 20250216202845.png]]

![[Pasted image 20250216203343.png]]

![[Pasted image 20250216204305.png]]

![[Pasted image 20250216204350.png]]
- ESM on the right, CommonJS on the left

![[Pasted image 20250216204453.png]]

![[Pasted image 20250216204518.png]]


*If you add novalidate tag to a form, the browser will send the form anyways, regardless of frontend validation!!!*
`<form action="required" ... novalidate>`

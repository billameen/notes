# Handling HTTP Requests


`app.use(express.static('public'))`


- First parameter is the about, then you provide a series of callbacks / middleware functions
	- Its like 
![[Pasted image 20250209232525.png]]
https://expressjs.com/en/4x/api.html#app.METHOD



# Middleware
- code that sits between the client and the routes
- they can do input validation, user authentication, etc.
![[Pasted image 20250209232704.png]]

![[Pasted image 20250209232757.png]]
![[Pasted image 20250209233007.png]]
![[Pasted image 20250209233211.png]]
![[Pasted image 20250209233301.png]]
- if middleware is attached to the entire app, it is called for all routes
![[Pasted image 20250209233604.png]]


# Serving Backend Content

![[Pasted image 20250209233802.png]]

![[Pasted image 20250209234015.png]]

![[Pasted image 20250209234231.png]]
![[Pasted image 20250209234345.png]]


# Handling HTTP Requests


`app.use(express.static('public'))`


- First parameter is the about, then you provide a series of callbacks / middleware functions
	- Its like 
![img](<images/Pasted image 20250209232525.png>)
https://expressjs.com/en/4x/api.html#app.METHOD



# Middleware
- code that sits between the client and the routes
- they can do input validation, user authentication, etc.
![img](<images/Pasted image 20250209232704.png>)

![img](<images/Pasted image 20250209232757.png>)
![img](<images/Pasted image 20250209233007.png>)
![img](<images/Pasted image 20250209233211.png>)
![img](<images/Pasted image 20250209233301.png>)
- if middleware is attached to the entire app, it is called for all routes
![img](<images/Pasted image 20250209233604.png>)


# Serving Backend Content

![img](<images/Pasted image 20250209233802.png>)

![img](<images/Pasted image 20250209234015.png>)

![img](<images/Pasted image 20250209234231.png>)
![img](<images/Pasted image 20250209234345.png>)


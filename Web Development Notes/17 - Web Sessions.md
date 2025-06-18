# Sessions
- A session is a series of related request coming from the same client
	- Not to be confused with authentication
- Sometimes we want to maintain some data within a session
	- Give our app "short term memory"
		- Recent history of user's actions
		- shopping cart
		- User preferences
	- Analytics and tracking

## Problem: The HTTP Protocol is Stateless
- How can we maintain state across requests?

1. We can keep some state in the client that will persist across page navigations
	- This involves keeping the state in the client
2. We can keep some state in the backend as long as we can identify who is making a request


# Web Storage API

- Allows storage of key/value pairs on the browser

- Two APIs implement the `Storage` interface
	- `localStorage`
	- `sessionStorage`

- Only strings can be stored
	- Objects can be stored as JSON strings

## `Storage` Interface
![[Pasted image 20250304163703.png]]

## LocalStorage vs SessionStorage

- `localStorage`
	- Stores data on the browser for a specific **origin**
		- An origin is the combination of scheme, host and port
		- ex. http:// , localhost, port 80 → encompasses a single origin. If any value is different, thats another origin.
		- This protects the localStorage from being accessed by another website
	- Data is stored indefinitely
		- The user can clear it manually
		- Browser keeps it there as long as there is enough space
- `sessionStorage`
	- Similar to `localStorage` but data is cleared when the **page session** ends
		- when the user closes the page (eg tab)
		- When the user closes the browser

## Limitations
- Remember that `localStorage` and `sessionStorage` are browser APIs
	- They can only be used on the browser, not NodeJS
	- Your backend cannot read values stored here directly

	- But your client can choose to send data to the server
		- Via HTTP payloads or query parameters
		- via HTTP headers

- Data stored via these APIs are vulnerable to XSS attacks
	- Malicious JavaScript running on your page can read data


# HTTP Cookies

- Cookies are small pieces of data that servers ask clients (browsers) to store
- The server gives a cookie a name, data, and optionally some parameters to configure how the cookie is handled by the browser
- Clients then send these data to the server with every request
	- The server can send unique data to each client to identify it
- HTTP Headers are used to transmit cookies

![[Pasted image 20250304164909.png]]


## Cookies for Server-side Sessions

- How it works:
1. If a client does not have a session, generate a unique identifier and send it in a cookie
2. Store user data (in like a database or smthn) on the server associated with each identifier (eg. in a dictionary keyed by the unique identifier)
3. Every time the client sends a request with this cookie, the server can identify the user from the data stored on the server for that identifier

- The client only sees an identifier. No other data is available to the client by default

## Cookies in Express
![[Pasted image 20250304170001.png]]

## A Little Help From Middleware
![[Pasted image 20250304170149.png]]


# Cookie Attributes

## Cookie Expiration
![[Pasted image 20250304170801.png]]

## HTTP-only Cookies
![[Pasted image 20250304170910.png]]

## Secure Cookies
![[Pasted image 20250304171126.png]]

## Limiting Cookie Scope
![[Pasted image 20250304230916.png]]

## Cross-site Behavior
![[Pasted image 20250304231123.png]]
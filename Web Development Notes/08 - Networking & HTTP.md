
- Protocol:
	- a networking protocol is a set of rules that determine how data is transmitted
	- communicating parties know the protocol in advance
	- They are used to encode and decode outgoing and incoming messages
	- they are usually built on top of multiple protocols

- Internet Protocol Addresses
	- Logical Addressing
	- used to uniquely identify networks and hosts within networks

	- a public ip address is one that is accessible by anyone on the Internet
	- A private or internal IP is only accessible within a network
	- 127.0.0.1 - localhost
	- 0.0.0.0 - usually refers any IP address on the host, like a wildcard

- Sockets
	- A socket is an OS-level network endpoint used to send and receive data
		- server socket binds an IP to a port under a protocol to listen for incoming network connections
		- A client socket establishes a connection
	- A socket address is a structure consisting of:
		- The transport protocol
		- IP address
		- Port number

- Port numbers
	- Identifies an OS process as a networking endpoint
		- Allows multiplexing a single connection
	- Its a 16-bit number: 0-> 65535
		- Ports 1-1023 are reserved

- Domains and DNS
	- A domain name (hostname) is a string that generally identifies an IP resource
		- ex: ncsu.edu resolves to 152.1.27.202
	- A domain name system (DNS) server is a service that provides resource records (eg. IP address) for a given domain name
	- For our purposes, we will use this for getting the corresponding IP address from a given domain name

---
## Introduction to HTTP

 - Protocol: how data is transmitted
 - Host: where the data is
 - Resource: what data we want

- Request (hey NCSU, send me the about page via a secure HTTP connection)
- Response (JS, CSS, HTML)


- Hypertext Transfer Protocol (HTTP)
	- Text-based application-level protocol
		- human readable, human writable
	- Content can be encrypted (HTTPS) or unencrypted (HTTP)
	- know:
		- HTTP request methods and their purpose
		- HTTP response status codes and their meaning

## HTTP Requests and Responses
- HTTP Request
	- A request line
		- HTTP request method
		- Path of resource being requested
		- protocol version
	- Zero or more headers
	- Optionally, a message body
		- depends on the type of request
![img](<images/Pasted image 20250202231823.png>)


- HTTP Response
	- A response line
		- protocol version
		- status code
		- status message
	- A series of headers
	- Usually, a message body
![img](<images/Pasted image 20250202231928.png>)


- HTTP Response Status Codes
	- 1XX: Information
		- 101 Switching Protocols
	- 2XX: Success
		- 200 OK
	- 3XX: Redirection
		- 301 Moved Permanently
	- 4XX: Application Error
		- 403 Forbidden
	- 5XX: Server Error
		- 500 Internal Server Error


## HTTP Request Method

- GET Request Method
	- used to retrieve data from a server
	- should not contain a body
- POST Request Method
	- Used to send data to the server
	- Generally used to create data
		- not idempotent
	- Typically contains a body
		- Body is the data being POSTed
- PUT Request Method
	- Used to send data to the server
	- Generally used to update data in place
		- Idempotent
	- Typically contains a body
	- Example:
		- updating an existing entry
- DELETE Request Method
	- Used to remove data on the server
	- Idempotent
	- May contain a body

Other HTTP Methods
- HEAD
	- like GET but excludes body
- OPTIONS
	- Identifies HTTP methods supported
- PATCH
	- Like PUT but for partial updates
- TRACE
	- obtain information about message's path to reach a resource



## HTTP Headers
- Headers carry additional infoprmation about a request/response
	- clients set request headers
	- servers set response headers
- Format: header-name: value
	- Name is case-insensitive
	- colon can be followed by a space
	- Value ends in a CRLF (carriage return, line feed)

- MIME Types
	- MIME: Multipurpose Internet Mail Extensions
		- Indicate the neature and format of a resource
		- `Type/subtype[;parameter=value]`
		- Example: text/plain;charset=UTF-8
	- Used by browser to determine how to process a resource
		- Examples:
			- HTML: text/html
			- CSS: text/css
			- JavaScript: text/javascript
			- Images: image/png, image/jpeg, image/gif
			- Videos: video/mp4

![img](<images/Pasted image 20250202233212.png>)





- `nslookup <domain>`
	- DNS Lookup
	- Gets the IP address of a server domain   

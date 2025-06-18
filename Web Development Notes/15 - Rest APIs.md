### API
- An API exposes data and functionality to external parties
- Examples
	- DOM API
	- Github API

## API Protocols Over HTTP
- SOAP: Simple Object Access Protocol
	- XML, wrapping content calls in objects in xml
- RPC: Remote Procedure Calls
- REST: Representation State Transfer
- GraphQL: Graph Query Language
	- Modern version of API through HTTP

# REST
- Most used HTTP API architectural style right now
	- Easy and flexible to implement
	- Maps well to HTTP methods
- Create, Read, Update, Delete

- REST Stands for REpresentational State Transfer
- URLs( endpoints) identify resources we want to perform operations on
	- Eg. `/users`
- Operations to perform are defined by the HTTP request method
	- `GET, POST, PUT, DELETE`, etc.
- Results of operations are indicated via HTTP response codes

## REST Design Principles
- Uniform Interface: endpoints are descriptive and follow a convention for resource identification
	- Relationships are very clearly outlined
- Client Server Decoupling: separation of concerns
	- Client can be anything, and client interacts with server through http
- Statelessness: each request has enough information to process it
	- All data needed for operation are given
	- data like authentication, data that needs to be processed, object that is being acted upon are part of the request itself
- Cacheability: responses can indicate if they can be cached to reduce the total number of requests
	- Can the client store the request for reuse
	- it exists to optimize the request
- Layered System Architecture: REST is just an interface layer that abstracts underlying complexities
	- Clients do not need to know or care if they are interacting with one or multiple servers, etc.
	- Clients are only concerned with API endpoints
	- reduces complexity

## REST Endpoint Design
- Routes should use plural nouns
	- HTTP methods are already verbs
	- Examples:
		- GET /counties
		- POST /counties
		- GET /parks/:id
- Nesting endpoints should follow relationships
	- Examples:
	- GET /counties/:county/parks to get all parks from county in variable :county
- the parts of the routes with : in the front of it is called a route parameter
	- express will take that value and put it in the `params` variable
![[Pasted image 20250225225820.png]]

# Backend Routing

![[Pasted image 20250225230128.png]]

![[Pasted image 20250225230318.png]]

![[Pasted image 20250225230419.png]]

![[Pasted image 20250225230516.png]]

![[Pasted image 20250225230714.png]]t
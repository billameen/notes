# Authentication Concepts

## Authentication vs Authorization

| Authentication                                                       | Authorization                                                                                                                                                 |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Do we know who the user is?                                          | Can the user access this resource?                                                                                                                            |
| Is the user who they say they are?                                   | What actions are the user allowed to perform                                                                                                                  |
| Verify who they are                                                  | Verify if they can use it                                                                                                                                     |
| Process of verifying the user (or a system) is who they say they are | May or may not require user authentication<br>- Some resources may be public, which is itself an authorization policy<br>- Authorization based on affiliation |
| On error, return `401 Unauthorized`                                  | On error, return `403 Forbidden`                                                                                                                              |

## Cryptographic Hashing Function
- Deterministic algorithm that produced a fixed-size bit array from input data
	- The same input always produces the same output
	- The output cannot be feasibly reversed to determine generating input
	- A small change in the input produces a big change in the output
- Example: SHA-256

## Username & Password
- The username uniquely identifies the user
- The password is used as a way for the user to prove that they should be authorized to operate under that username
- When sending passwords over the network, we must always use an encrypted connection (HTTPS)

## Considerations When Creating New Users
- When storing a new user, we save the user's username and password
	- But what if our database gets compromised?
- Passwords should NEVER be stored in plain text
	- Hashes should be used instead

- Problem: rainbow tables - precomputed hashes of common words or phrases, or even all possible strings up to a certain length
- Improvement: have an application secret key that gets combined with the user's password before hashing
	- Instead of `hash(password)` do `hash(secret_key + password)`

## Problem: Users With The Same Password

- If our database gets compromised, an attacker will know that these two users share the same password
	- If a CEO and a random user have the same password, some hacker can social engineer the password of the random user, and then get the password of the CEO
- We want to be able to have unique password hashes for each user, even if they share a common password

### Solution: Salt
- Unique random value for each user
	- Instead of 
		`hash(secret_key + password)`
		do
		`hash(salt + password)`
- The salt itself does not need to be kept secret, but has no meaning or purpose outside of obfuscating the hash

## Choosing a Hashing Function for Passwords
- Most hashing functions are designed to be as fast as possible
	- This makes it easier to conduct brute force attacks
- Some hashing functions have identified weaknesses
- Prefer password-specific hashing functions like Argon2, Bcrypt, Scrypt, or PBKDF2
	- Designed to be slower to defeat brute force attacks, often via parametrized repeating hashes
	- Designed with salts in mind

---
## Creating a New User
1. Receive user details, including username and password
	- Make sure user doesn't exist already
2. Generate a random salt for the user
	- 128-bit +
	- Cryptographically random value per user
3. Hash the user's password with the salt
	- Use a password-specific hashing function
4. Store the user details, salt and hashed password (never the password itself)
---
## Authenticating a User
1. Receive the user's username and password
2. Retrieve the user's unique record by matching the username
	- This will contain the password hash
3. Use the user's provided password + the salt on the user's record to generate a password hash
	- You will need to use the same hashing function with the same parameters
4. Compare the generated password hash to the password hash on the user's record

--- 
# Session Authentication

- The server initializes a session when the user logs in
	- A session ID is generated and given to the client
- The server keeps track of the mapping between a session ID and the user
- The client sends the session ID to the server on every request
	- The server can then use this ID to identify the user and associated data
- The server can clear a session to "log out" the user
	- The user can also request that a session be cleared

![img](<images/Pasted image 20250316145816.png>)

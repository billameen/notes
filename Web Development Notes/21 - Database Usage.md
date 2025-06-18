# Date Normalization

![[Pasted image 20250325222814.png]]

## Designing for Normalization
![[Pasted image 20250325223043.png]]
- This one satisfies 1NF, but it could be better

![[Pasted image 20250325223147.png]]

![[Pasted image 20250325223418.png]]


---
# SQL Operations & JOINs
![[Pasted image 20250325223556.png]]


![[Pasted image 20250325224458.png]]
- For no fields, it assumes that the values you provided are in the order of the values of the columns of the table
- For using field defaults, the database has auto-incrementing fields w default values
- For full, the values provided in the parenthesis after `park` must correspond to the column names

![[Pasted image 20250325224932.png]]

![[Pasted image 20250325225331.png]]

![[Pasted image 20250325225558.png]]
- its like an AND operator between tables

![[Pasted image 20250325230050.png]]
![[Pasted image 20250325230121.png]]
- these do the same thing as JOIN, but retains all values
- the difference between right and left is just the order in which the tables get combined

![[Pasted image 20250325230345.png]]
- `LIKE` operator is like a substring matcher
- `W%` → checks if a par_name starts with the letter "W"
	- the `%` sign is like a wildcard


![[Pasted image 20250325230655.png]]



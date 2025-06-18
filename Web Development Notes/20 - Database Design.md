
# Introduction
![[Pasted image 20250323224843.png]]

![[Pasted image 20250323224906.png]]

![[Pasted image 20250323224923.png]]
 ![[Pasted image 20250323225006.png]]

![[Pasted image 20250323225218.png]]

![[Pasted image 20250323225323.png]]

![[Pasted image 20250323225535.png]]


# Primary & Foreign Keys

![[Pasted image 20250323225755.png]]

![[Pasted image 20250323230410.png]]

![[Pasted image 20250323230424.png]]

![[Pasted image 20250323230553.png]]

# Basic Data Modeling

## Choosing Attributes
### Calculated Data
- avoid data that can be calculated
	- ex. age → store birthdays instead, age changes each year
### Break Down Complex Values
- ex. dont store the entire address as a string, store the individual parts of the address so it is easier to query

### Allocate Appropriate Precision
- ex. don't store zip codes using 200 characters, you only need at most 10
- ex. don't store a year using 100 characters, you only need 4
- This makes thinks more efficient, in terms of both query speed and global storage

![[Pasted image 20250323231408.png]]

![[Pasted image 20250323231427.png]]



### Example
![[Pasted image 20250323231508.png]]
 ![[Pasted image 20250323231617.png]]
![[Pasted image 20250323231811.png]]


---
# Cardinality
- How many things are related to other things

## One-to-one
![[Pasted image 20250323232004.png]]
![[Pasted image 20250323232035.png]]

## One-to-many
![[Pasted image 20250323232143.png]]

## Many-to-many
![[Pasted image 20250323232210.png]]
- Allows books to have multiple authors and authors having multiple books


![[Pasted image 20250323232542.png]]
- This many-to-many relationship has attributes
- in this case, the reservation has properties to describe the guest-room relationship

![[Pasted image 20250323232308.png]]
- This allows multiple guests on the same reservation
- allows multiple rooms per reservation and multiple guests per reservation

## Recursive Relationships
![[Pasted image 20250323232345.png]]
- Categories and subcategories
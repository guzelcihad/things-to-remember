Elements of an ER model
* Entity types
* Attributes
* Relationships
* Subtypes


![alt text](images/68.PNG)

![alt text](images/69.PNG)

# Normalization

## 1NF
Practically we use 3rd normal form.

- Each table cell should contains a single(atomic) value
- Each record needs to be unique

![alt text](images/70.PNG)

At the end
- Split columns to atomic values
- If multiple values can be assign to a record, move them to a new table

![alt text](images/71.PNG)

![alt text](images/72.PNG)

## 2NF
A table is in 2NF if it is in 1NF and every non-key attribute of the 
table is dependent on the whole(every attribute of the) composite primary key.
- Tables without composite primary key are in the 2NF by default

For ex: warranty belongs to product table, move it.
![alt text](images/74.PNG)

## 3NF
Applies every non-prime attribute of the table must be dependent on primary key, or
we can say that, there should not be the case that a non-prime attribute is 
determined by another non-prime attribute. So this transitive funtional
dependency should be removed from the table and also the table must be in 2NF

For ex: brand is more dependent on the brand than the product
![alt text](images/75.PNG)

# Identifying Relationship vs Non-identifying Relationship
- Identifying -> Existence of a row in a child table depends on the parent table
For ex: a person has one or more phone numbers. So we need to keep it separate table.
<br>
In mysql it creates person id in phone numbers and phone id - person id together composite pk.

![alt text](images/76.PNG)
In practice we use non identifying by default.

# Cardinality
![alt text](images/77.PNG)
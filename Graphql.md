## What is GraphQL?
A query language for API and a runtime for fulfilling those queries. <br>
We give clients the power to ask what they exactly need.


<br>
It is a collection of three things:

* Schema definition language or SDL
* Runtime environment
* Query language

## SDL
Used to define graphql schema.<br>
Schema is used to expose the functionalities that are available in an application to its users.
<p>
A Schema contains:

* Types which are similar to classes in Java
* Operations which can be performed on these types.

```
type Query{
    getBook(id:Int):Book
    getBooks:[Book]
}

type Mutation{
    createBook(name:String, pages:Int):Int
}

type Book{
    id:Int
    name:String
    pages:Int
}
```
## Runtime Environment
Performs two major operations:

* Parsing the schema file and creating in memory schema from it.
* Executing the operation specified in the request

## Query Language
Used by clients to perform actions on API

## Data Fetcher
Call back function, linked to every query.

## Efficiency
There are lots of challenges of modern APIs. Versioning, security, documentation, efficiency and so on.<br>
For efficiency there are two common problems.

* Overfetching, response contained too much data
* Underfetching, response did not contain enough data. Make another network request.

It matters because networks suck.

<p>

* Avoid overfetching and underfetching
* Clients to declare all the data they need in a single network request
* Reduces the need for client-side joins, error handling, retry logic


## Concepts
SDL

- Define a one to many relation
![alt text](../images/99.PNG)

- Queries to get data
![alt text](../images/100.PNG)

### Mutations
3 kinds of mutations
- creating new data
- updating existing data
- deleting existing data

![alt text](../images/101.PNG)

### Subscriptions
It is like websocket connections

![alt text](../images/102.PNG)

We put all together to define an API to create a contract between client and server

![alt text](../images/103.PNG)

![alt text](../images/104.PNG)

![alt text](../images/105.PNG)

### Queries With Arguments
In GraphQL, each field can have zero or more arguments if that’s specified in the schema. For example, the allPersons field could have a last parameter to only return up to a specific number of persons. Here’s what a corresponding query would look like:

```
{
  allPersons(last: 2) {
    name
  }
}
```

# Architecture
Graphql is a specification. You need to create graphql server

## Resolver functions
![alt text](../images/106.PNG)

## Graphql clients
![alt text](../images/107.PNG)

# Graphql Client
There are two major GraphQL clients available at the moment. The first one is Apollo Client, which is a community-driven effort to build a powerful and flexible GraphQL client for all major development platforms. The second one is called Relay and it is Facebook’s homegrown GraphQL client that heavily optimizes for performance and is only available on the web.
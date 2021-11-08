Agile product launch
* Because each microservice can be a separated component, you can deploy it independent of other services.
*  This means if a microservice has bugs, we can isolate the issues to that particular service and still keep other clean services running.
* You only need to target that particular service with bugs, and not the entire monolithic application.

Smaller 2-pizza teams
* In agile development, there is a two-pizza rule for teams. If a team need more than 2-pizzas to feed itself, then that team is too big!
* Larger teams have too much management overhead and communication channels

Manageable code base
* Technical debt from a large code base is wasteful
* Larger code bases are harder to debug and manage
* Microservices split the code into smaller units
* It's easier to add features, since not all components are so intertwined

Polyglot computing
* This architecture leaves more flexibility in terms of team formations and even choice of languages each team may use
* It is common to have a final microservices architecture with Javascript, Ruby, Python, and Java-based web frameworks all servicing different needs.

Better fault-handling
* Each service is decoupled
* A failure in one part of the service will be isolated and not affect the other parts

Decoupled databases
* This makes any changes to the data schemas separated among services

Scalable infrastructure
* Can be horizontally or vertically scaled
* Easier for instances of heavy-traffic spikes or when teams need more computing power

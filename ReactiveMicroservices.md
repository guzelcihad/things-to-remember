Every architectural decision has a trade off

A group of engineer came together in September 2014 to publish
a manifesto encouraging a unified and principle approach
for solving the modern demands of todays application. Reactive Manifesto

# Responsive
Responsive systems provide timely responses agains customer interaction.

# Resilient
A systems ability to stay responsive under failure.
Resiliency achieved by these terms:

## Replication
A group of replicated groups, load evenly balanced

Resilience in practice, remember Circuit Breaker

# Elastic
Elasticity is not scalability.
Scalability is the measure of a components ability to increased workloads.
Elasticity, on the other hand, can be defined as two way scalability.
The measure of the components ability to handle both increased and decreased workloads.
Elasticity is generally achieved by sharding, replication and workload distribution.

# Message Driven
Defines a protocol whereby applications can be decoupled from one another.

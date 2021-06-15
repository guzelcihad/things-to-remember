The philosophy of domain-driven design (DDD) is about placing
the attention at the heart of the application, focusing on the complexity
of the core business domain. Alongside the core business
features, you’ll also find supporting subdomains that are often
generic in nature, such as money or time. DDD aims to create models
of a problem domain. All the implementation details—like persistence,
user interfaces, and messaging—come later. The most crucial
thing to understand is the domain, because this is what a majority
of software design decisions are going to be based on. DDD
defines a set of concepts that are selected to be implemented in software,
and then represented in code and any other software artifact
used to construct the final system.<p>

Working with a model always happens within a context. It can vary
between different requirements or just be derived, for example, from
the set of end users of the final system. The chosen context relates to
the concepts of the model in a defined way. In DDD, this is called
the bounded context (BC). Every domain model lives in precisely
one BC, and a BC contains precisely one domain model. A BC helps
to model and define interactions between the BC and the model in
many different ways. The ultimate mapping for the model is the
inside view of the one related BC.<p>

Assuming we already have a layered application approach (e.g., presentation,
application, domain, infrastructure), DDD acts on the
domain layer. While the application layer mostly acts as a mediator
between presentation, domain, and infrastructure (and holds additional
crosscutting concerns, such as security and transactions), the
domain layer only contains the business objects. This includes the
value objects themselves and all related artifacts (e.g., property files,
translations) and the module structure, which typically is expressed
in packages (e.g., in Java) or namespaces.<p>

Entities, values, and modules are the core building blocks, but DDD
also has some additional features that will help you to model your
application so that you can build it from domain services. A domain
service corresponds to business logic that does not easily live within
an entity or it can act as a proxy to another BC. While a domain service
can both call or be called by a domain entity, an application service
sits above the domain layer, so it cannot be called by entities

## Another definition
It’s interesting how some methodologies and techniques take years
to “mature” or to gain awareness among the general public. And
Domain-Driven Design (DDD) is one of these very useful techniques
that is becoming almost essential in any discussion about
microservices. Why now? Historically we’ve always been trying to
achieve two synergic properties in software design: high cohesion
and low coupling. We aim for the ability to create boundaries
between entities in our model so that they work well together and
don’t propagate changes to other entities beyond the boundary.
Unfortunately, we’re usually especially bad at that.
<p>

DDD is an approach to software development that tackles complex
systems by mapping activities, tasks, events, and data from a business
domain to software artifacts. One of the most important concepts
of DDD is the bounded context, which is a cohesive and welldefined
unit within the business model in which you define the
boundaries of your software artifacts.
<p>

From a domain model perspective, microservices are all about
boundaries: we’re splitting a specific piece of our domain model that
can be turned into an independently releasable artifact. With a badly
defined boundary, we will create an artifact that depends too much
on information confined in another microservice. We will also create
another operational pain: whenever we make modifications in
one artifact, we will need to synchronize these changes with another
artifact.<p>

We advocate for the monolith-first approach because it allows you
to mature your knowledge around your business domain model
first. DDD is such a useful technique for identifying the bounded
contexts of your domain model: things that are grouped together
and achieve high cohesion and low coupling. From the beginning,
it’s very difficult to guess which parts of the system change together
and which ones change separately. However, after months, or more
likely years, developers and business analysts should have a better
picture of the evolution cycle of each one of the bounded contexts.<p>


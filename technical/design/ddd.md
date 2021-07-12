# Domain Driven Design (DDD)  

Eric Evans is credited with having developed the concept of DDD.

At its heart DDD intends to produce software written in a way that is strongly grounded on the concepts and thinking of the software's problem space - the domain. Its ultimate motivation for this is to reduce the complexity of the software, the premise here being simpler software is modelled on real-world thinking in the problem space. To achieve this the programmers focus needs to shift from communicating to the computer to communicating to the reader using language and concepts grounded in the problem space. Producing software with this focus requires programmers, and indeed all team members, to gain a deep knowledge of the domain. DDD is arguably poorly named as it is far more than an approach to software *design*.  It is an approach to software development in general that influences:

- What software to write: what problems should the software you develop solve, why choose these problems?
- How to structure software teams: from a resource planning point-of-view, how can you structure teams so that they can work autonomously?
- Virtually the entire [software development lifecycle (SDLC)](https://en.wikipedia.org/wiki/Systems_development_life_cycle): DDD offers analysis techniques, architectural patterns, design techniques and implementation patterns, and as such touches virtually all SDLC phases.

The sections that follow provide some introductory detail on key aspects of the DDD approach to software development.

### Purpose Alignment Model

We only have a finite capacity to write software, so what software should we write?  What software is critical to our success - to our customers choosing our software over our competitors?
DDD categorises domains into a set of types, where each type is of different value to the organisation:

- **Core domains**: Those domains which customers ultimately choose to purchase your software for, which aim to offer innovative and differentiating experiences in the marketplace.
- **Strategic domains**: Those domains which support the *core*, but are not in themselves market differentiating.  These domains likely warrant custom development to support the core, but may be outsourced and are less worthy of investment.
- **Generic domains**: Those domains where software can be purchased to fulfil the job as they have been productised / commoditised.

DDD proponents often talk of using the [purpose alignment model](https://www.alaska.edu/files/pathways/WhitePaperonPurposeBasedAlignmentModel.pdf) as a way to visualise and decide on those domains that warrant investment in writing custom software.

### Event Storming

[Event storming](https://en.wikipedia.org/wiki/Event_storming) is an analysis technique aimed at understanding the roles of systems in fulfilling user scenarios.  It aims to:

* Map-out the flow of activities needed to realise user scenarios, with the events - the data changes that must happen within the systems - being most prominent in terms of what it captured.
* Have team members work with with domain experts in a very dynamic and engaging way to uncover the needs of systems in handling the key concerns of the domain.

As an example scenario, a user purchasing software online will instigate a flow of many activities in systems - billing and invoicing systems need to charge the user and send tax receipts, an account will need to be provisioned in order for the user to access the software.  Events such as *product purchased*, *invoice sent*, *invoice paid* and *account provisioned* would be examples of key events in this scenario. 

### Context Maps

[Context maps](https://en.wikipedia.org/wiki/Domain-driven_design#Context_map) are a design visualisation technique that captures the domains of a system and the relationships between them.
They provide insight into the responsibilities of domains in a context, such as a sales context that holds a customers billing information.

[Bounded contexts](https://martinfowler.com/bliki/BoundedContext.html) extend context maps to visualise the differences between contexts.
For example, product and sales contexts need data about a customer but the nature of the data differs - a product context needs access rights, whereas a sales context need purchase history.
Recognising these differences between contexts helps in forming teams and software that is able to move independently of each other, and therefore move more efficiently.

DDD goes so far as to categorise the types of relationships between teams working at domain integration points.  These categories describe the team in control of the language, which ultimately reflects who is in control of shaping system API's:

- **Shared Kernel**: Where a domain is shared across teams and thus strong development collaboration takes place.  All teams are in control of the language and must be made aware of changes.
- **Customer-Supplier**: Where a consumer (customer) is in control of the language and negotiates changes with a producer (supplier).  The producers language is subservient to the needs of consumers.
- **Conformist**: Where a producer is in complete control of the language and typically works in complete isolation from consumers, resulting in an API that may not particularly geared to consumer needs - consumers may be forced to 'conform' with potentially inefficient or cumbersome API's that result from this relationship. 
- **Open Host Service**: Where a producer is in control of the language but consults with consumers to determine what this should be, publishing a generic API for consumption that is mindful to the needs of consumers. 

### Domain Models

[Domain models](https://en.wikipedia.org/wiki/Domain_model) are both a design visualisation technique and approach to designing a system that intend to solve the problems of a *particular domain only*.
From a design approach point-of-view it is often used as a verb 'domain modelling', which aims to place the domain front-and-centre in the design such that the concepts of the domain are explicitly captured and central to a produced design.
The produced design is captured in a object model diagram which is called a 'domain model', which constitutes the design visualisation point-of-view.

A model is typically formed and refined in consultation with domain experts to better ensure the naming of concepts and their relationships are truly representative of the problem space.

#### Domain Model Elements: Value Objects, Entities and Aggregates
DDD categorises the elements of a domain model into [entities, value objects and aggregates](https://lostechies.com/jimmybogard/2008/05/21/entities-value-objects-aggregates-and-roots), each having different levels of importance in the model and describing the nature of the data they hold.
Importantly in a domain driven design, the elements are considered to not just to hold data but also contain the operations that can be performed on the data. 

##### Value Objects
A value object describes a simple value, likely a composite data structure, such as an address which is composed of city, state and country.
It distinguishes itself from the other elements of a domain model because the value is immutable - for instance, a particular address in the world cannot have its geo-coordinates change.

##### Entities
An entity is an object whose identity is immutable but has state that is mutable.
For example a person entity whose data includes name and social security number - the name is mutable, however the social security number is immutable and can be used to distinguish a particular person from any other, thus acting as a person *identifier*.

##### Aggregates
An aggregate contains many entities and value objects, often having a facade to simplify interaction with these underlying elements.
They are particularly distinguished from other elements of a domain model because they represent data consistency and transactional boundaries - if any data within an aggregate changes the entire aggregate must change for the system the remain consistent.
For example, lets say a family is modelled as an aggregate composed of people and that a families size was persisted for performance reasons.  In order to ensure the size is correct, when a family member is added or removed we would want the size and family member change to be persisted in the one transaction.

##### Services
In DDD terms a service is distinguished from other domain model elements as it contains no state - it is a place for an operation that does not conceptually lie in the other element types.

#### Domain Element Lifecycle Patterns: Factories and Repositories 
DDD talks to the lifecycle of elements in a model, and promotes a design for how things are created, persisted, reconstituted from persistent state and destroyed.

##### Factories
Factories, ala the conventional [factory pattern](https://en.wikipedia.org/wiki/Factory_(object-oriented_programming)), are the place in a design where domain elements are born or created.  Entities and aggregates often benefit from these as their creation logic tends to evolve to be non-trivial.

##### Repositories
Repositories are akin to a [Data Access Object (DAO)](https://en.wikipedia.org/wiki/Data_access_object) in that they provide an interface that encapsulates interaction with a persistence technology.  In this way they provide the way for domain elements to be saved, reconstituted from that saved state and ultimately destroyed / end-of-life'd.

### Domain Anti-Corruption
Domain purity and *anti-corruption* is a key concept in DDD thinking.

The idea here is that the domain model should not be impacted by the concerns of software integration.  For example, when a model is being persisted to a datastore, the concerns of the store should not leak into the domain, such as database entity naming conventions or a heavily normalised or denormalised database structure.  The same thinking applies when integrating systems, the data required of a product in a billing system should not *corrupt* the data needed in a shop-front where the user purchases the product.

This purity of domain is often achieved through an implementation pattern known as an *anti-corruption layer*.

### Ubiquitous Language
This stands-out as the most fundamental concept of DDD.  A *ubiquitous language* is one that is shared by all roles and the wider organisation.  It is used in all documentation and assets, including code.

Having this common language lessens the chance of confusion and misinterpretation - it affords collaboration efficiencies.  It is also central to having the software represent real world thinking in the problem space, it is a conduit for that vocabulary to pervade into the software.
With a good ubiquitous language those in a product role are better able to reason about the software, whilst those in developer roles are better able to understand requirements and the problem domain in general.

Another key point here, DDD promotes naming in software that more influenced by the domain and less by technology, tooling and patterns choices.  For example, a class name such as Product is more preferred than ProductModel.

### Knowledge Crunching and Refactoring
DDD acknowledges that good designs and implementations are evolutionary.

Through a teams experiences their knowledge of a domain will grow over time, leading to insights that can simplify and improve the systems design and implementation.
DDD encourages teams to incorporate this knowledge into the software through [refactoring](https://en.wikipedia.org/wiki/Code_refactoring), exploring better ways to express the domain and problem being solved.
In areas where a design does not feel right, DDD encourages teams to *crunch knowledge* in the domain and explore other concepts in the domain that can aid the design.

### Blog posts to read
- [Domain Driven Design - what is it and how do you use it?](https://airbrake.io/blog/software-design/domain-driven-design)
- [The Purpose Alignment Model - applied to software](http://toddlittleweb.com/wordpress/2014/06/22/the-purpose-alignment-model/)
- [Event Storming - the initial concept](http://ziobrando.blogspot.com.au/2013/11/introducing-event-storming.html)
- [About domain models and context maps](http://culttt.com/2014/11/19/bounded-contexts-context-maps-domain-driven-design)
- [About value objects, entities and aggregates](https://lostechies.com/jimmybogard/2008/05/21/entities-value-objects-aggregates-and-roots)
- [About ubiquitous language](https://blog.carbonfive.com/2016/10/04/ubiquitous-language-the-joy-of-naming)
- [Another curated list of DDD resources](https://github.com/heynickc/awesome-ddd)

### Videos to watch
- [An animated introduction to DDD](https://www.youtube.com/playlist?list=PLIHVWAtJFACm4sffK5M_UxDg7k-xXI16F)
- [An overview of the DDD book](https://www.youtube.com/watch?v=lMtC4ITgOIw)
- [Reflections on modern DDD techniques - Tackling Complexity in the Heart of Software](https://www.youtube.com/watch?v=dnUFEg68ESM)

## More advanced stuff
DDD thinking has brought about several architectural patterns that are increasing in prominence and worthy of consideration for any system:
- [Command Query Responsibilitiy Seggregation (CQRS) - what is it?](https://martinfowler.com/bliki/CQRS.html)
- [Event Sourcing - what is it?](https://martinfowler.com/eaaDev/EventSourcing.html)

On how DDD thinking impacts resource planning and organisation structure:
- [Domain Driven Architectural Alignment](http://www.ustream.tv/recorded/102893159)

## Books to read
- [Domain Driven Design](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215)
- [Domain Driven Design Distilled](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420)
- [Event Storming (Alberto Brandolini)](https://leanpub.com/introducing_eventstorming)
- [Patterns, Principles, and Practices of Domain-Driven Design (Scott Millett)](https://www.amazon.com/dp/1118714709/)

## Courses
- [Modern Software Architecture: Domain Models, CQRS, and Event Sourcing](https://app.pluralsight.com/library/courses/modern-software-architecture-domain-models-cqrs-event-sourcing/)
- [Domain Driven Design Fundamentals](https://app.pluralsight.com/library/courses/domain-driven-design-fundamentals/table-of-contents)

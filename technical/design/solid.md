# SOLID principles

SOLID is an acronym for five design principles that intended to make software more understandable, flexible and maintainable.

See [wikipedia](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) for a further background. 

## Five principles

### S - Single responsibility principle

Every module or class should have responsibility over a single part of the functionality provided by the software, and that 
responsibility should be entirely encapsulated by the module or class.

### O - Open / closed principle

Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification"; that is, such an 
entity can allow its behaviour to be extended without modifying its source code.

### L - Liskov substitution principle

Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.

### I - Interface segregation principle

No client should be forced to depend on methods it does not use. Interfaces that are very large should be split into smaller and more 
specific ones so that clients will only have to know about the methods that are of interest to them.

### D - Dependency inversion principle

High-level modules should not depend on low-level modules. Both should depend on abstractions.
Abstractions should not depend on details. Details should depend on abstractions.

## Examples

* [Mike Knepper (8th Light)](https://github.com/mikeknep/SOLID)
* [Single responsibility (DZone)](https://dzone.com/articles/solid-principles-by-examples-single-responsability?fromrel=true)
* [Opened / Closed (DZone)](https://dzone.com/articles/solid-principles-by-examples-openclosed)
* [Liskov (DZone)](https://dzone.com/articles/solid-principles-by-examples-liskov-substitution-p)
* [Interface segregation (DZone)](https://dzone.com/articles/solid-principles-by-example-interface-segregation)
* [Dependency inversion (DZone)](https://dzone.com/articles/solid-principles-by-example-dependency-inversion)

## Training Videos

* [SOLID Principles with Uncle Bob](https://cleancoders.com/videos/clean-code/solid-principles)
* [SOLID Principles of Object Oriented Design (Pluralsight)](https://www.pluralsight.com/courses/principles-oo-design)

## Blog posts to read 

* [From STUPID to SOLID Code!](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/)

## Expanding your understanding of SOLID

* [SOLID Clojure](https://www.infoq.com/presentations/SOLID-Clojure)  
* [Why every element of SOLID is wrong](https://speakerdeck.com/tastapod/why-every-element-of-solid-is-wrong)  
* [SOLID Princples of Object Oriented and Agile Design - Bob Martin](https://www.youtube.com/watch?v=TMuno5RZNeE)  
* [SOLID Deconstruction by Kevlin Henney](https://vimeo.com/157708450)  
* [Functional programming design patterns by Scott Wlaschin](https://vimeo.com/113588389)  

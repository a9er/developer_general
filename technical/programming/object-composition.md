# Object Composition

> The problem with object-oriented languages is they’ve got all this implicit environment that they carry around with them. You wanted a banana but what you got was a gorilla holding the banana and the entire jungle.
>
>_- Joe Armstrong, author of the Erlang programming language_

Object composition can (and should!) be used to avoid the problem alluded to in the quote above. When we wish to share functionality between multiple classes, instead of creating a single parent class we can

1. Create one or more smaller classes or interfaces that encapsulate the desired functionality (and adhere to the [single responsibility principle](../design/solid.md)!)
1. Include instances of these in the any new classes we wish to share functionality with
1. Expose the desired functionality by using these instances

## Practice Katas

- [Composition kata](https://github.com/OdeToCode/Katas/tree/master/Composition/CS/Composition)

## Things to read

### Online

- [Favor composition over inheritance - Part 1](https://codingdelight.com/2014/01/16/favor-composition-over-inheritance-part-1/)
- [Favor composition over inheritance - Part 2](https://codingdelight.com/2014/01/17/favor-composition-over-inheritance-part-2/)
- [Composition over inheritance: How to choose?](https://www.thoughtworks.com/insights/blog/composition-vs-inheritance-how-choose)
- [Composition over inheritance (Wikipedia)](https://en.wikipedia.org/wiki/Composition_over_inheritance)

### Books

- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612/)

## Videos to watch

- [Composition over inheritance](https://medium.com/humans-create-software/composition-over-inheritance-cb6f88070205)

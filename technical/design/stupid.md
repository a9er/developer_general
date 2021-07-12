# STUPID

Following [SOLID](./solid.md) principles helps us to write code that is understandable, flexible and maintainable. It is generally good to follow SOLID when doing object oriented programming. On the opposite side of the spectrum, we should also be mindful to avoid bad practices and learn from code we have written in the past. Some of these bad practices can be summed in a mnemonic known as STUPID.

## What is STUPID?

### S - [Singleton](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#singleton)
A design pattern that restricts the instantiation of a class to one object. It is considered an antipattern and should be avoided because:  
- Programs using global state are very difficult to test  
- Programs that rely on global state hide their dependencies  

Extra: [Singleton Patterns](https://en.wikipedia.org/wiki/Singleton_pattern)  

### T - [Tight Coupling](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#tight-coupling)
Tight coupling is when classes and objects are heavily dependent on each other. It reduces flexiblity and reusability of the application.  

Extra: [Understanding Loose Coupling and Tight Coupling](http://www.dotnet-stuff.com/tutorials/c-sharp/understanding-loose-coupling-and-tight-coupling)  

### U - [Untestability](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#untestability)
Untestability is when an application or program is difficult to test, usually caused by tight coupling.  

### P - [Premature Optimisation](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#premature-optimization)
Premature optimisation is the act of optimising before we know what we need to do. It can lead to unreadable code and a bad time.  

### I - [Indescriptive Naming](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#indescriptive-naming)
Programming languages are written for humans to understand therefore, it is best to name classes, methods and attributes properly. This means being descriptive, expressing intent and no abbreviations.  

Extra: [Stages of Naming](http://blog.markpearl.co.za/Four-Stages-Of-Naming)  

### D - [Duplication](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/#duplication)
Avoid duplicating code and keep it simple!  

## Resources
These blog posts go further into STUPID:
- [Don’t be STUPID: Grasp SOLID!](https://nikic.github.io/2011/12/27/Dont-be-STUPID-GRASP-SOLID.html)
- [From STUPID to SOLID code!](http://williamdurand.fr/2013/07/30/from-stupid-to-solid-code/)

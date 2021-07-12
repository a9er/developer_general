# Page Object Model

A *page object model* is a design pattern that applies to automated UI tests.

In terms of origins, Martin Fowler is credited with forming the basis of this pattern through the [window driver pattern](https://martinfowler.com/eaaDev/WindowDriver.html).  The [Selenium](http://www.seleniumhq.org) community later evolved the pattern and used the name *page objects*.

The general intention of the pattern is to explicitly model the artifact under test - in this case the UI.

Explicitly modelling the UI affords the following benefits:

- **Improves readability**: The tests language now involves interaction with pages rather than esoteric DOM navigation.  Interacting with the UI and asserting against its state is much more *intentional* by using this page language.
- **Encapsulates the UI**: Discovery of UI elements is isolated to one place, rather than duplicated across tests.  Consequently changes to the UI are less likely to propagate to tests and are most likely encapsulated to the UI models.

The pattern is an outcome of applying [SOLID](../design/solid.md) and [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principles to tests - these principles equally benefit tests as they do source code.
Whilst the pattern is geared around modelling the UI, similar benefits can be had for modelling other assets under test, say for example an API. 
  
### Blog posts to read 
- [Martin Fowler's explanation of the pattern](https://www.martinfowler.com/bliki/PageObject.html)
- [The Selenium community explanation of the pattern](http://www.seleniumeasy.com/selenium-tutorials/page-object-model-framework-introduction)

## More advanced stuff
- [Extending page objects with fragment and step objects](http://codecept.io/pageobjects)
- [A collection of good UI test practices](https://www.blazemeter.com/blog/top-15-ui-test-automation-best-practices-you-should-follow)
- [Page objects and advanced UI test patterns including screenplays](https://www.youtube.com/watch?v=ZoJ4c6sUcoQ)

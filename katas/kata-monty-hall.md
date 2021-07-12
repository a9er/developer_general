# Kata Monty Hall

This eponymous gameshow host tempts contestants with a big prize, hidden behind one of three doors. The contestant begins by choosing a door, but not opening it. Then Monty steps forward and opens one of the other doors. He reveals a goat (!). Then the contestant has the choice of either sticking with the door they have already chosen, or switching to the other unopened door. Whichever door the contestant decides on will be opened, and if they find the prize, they get to keep it. (I’m not sure what happens if they get the second goat!) So what’s the best strategy?

## The Monty Hall Dilemma

That’s the classic “Monty Hall Dilemma”. Should you keep to your original choice of door? You could try playing the game yourself using this [online version](https://math.ucsd.edu/~crypto/Monty/monty.html). People are biased towards sticking with what they’ve chosen, and the vast majority of people keep the door they originally picked. Intuitively there should be an equal chance of the prize being behind any of the three doors, so it shouldn’t matter if you stick or switch. However, in this case, your intuition is wrong. You are twice as likely to win the prize if you switch to the other unopened door.

Many people disbelieve this result, even famous mathematicians have refused to accept it. What is convincing is a computer simulation that proves it.

## What you need to do for this kata

* Your task is to write a computer simulation for this provlem that proves that switching doors is best - you will do this by simulating 1000 games using each strategy and comparing the winning percentage.
* You are going to do this using TDD and leveraging mocks or stubs. Read this essay by [Martin Fowler](http://martinfowler.com/articles/mocksArentStubs.html) about mocks and stubs for more info.

## Additional discussion points once you have completed it

* How did you setup your “guiding test” at the start? Did the interface you designed turn out to be a good one?
* How did you allow the tests to control the randomness of which door would have the prize?
* Did you use any mocks or stubs?
* How easily would your code cope if the number of doors were increased?
* Did you find mocks or stubs a better approach to tackle this kata?

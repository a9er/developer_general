# Yatzy Kata

The game of Yatzy is a simple dice game. Each player rolls five six-sided dice. They can re-roll some or all of the dice up to three times (including the original roll).  

## Task 

This Kata is quite easy for TDD beginners since the test cases are more or less enumerated in the problem description. The order to implement them in is not prescribed, though, so you can practice that aspect of TDD.

Do this kata again from scratch and tackle the test cases in a different order. Does this affect the design you end up with? Can you take the tests in any order at all?
If you’d like more practice at choosi

## The rules of the game  

For example, suppose a players rolls (3,4,5,5,2). They hold (-,-,5,5,-) and re-roll (3,4,-,-,2) to get (5,1,5,5,3). They decide to hold (5,-,5,5,-) and re-roll (-,1,-,-,3). They end up with (5,6,5,5,2).  

The player then places the roll in a category, such as ones, twos, fives, pair, two pairs etc (see below). If the roll is compatible with the category, the player gets a score for the roll according to the rules. If the roll is not compatible with the category, the player scores zero for the roll.  

For example, suppose a player scores (5,6,5,5,2) in the fives category they would score 15 (three fives). The score for that go is then added to their total and the category cannot be used again in the remaining goes for that game. A full game consists of one go for each category. Thus, for their last go in a game, a player must choose their only remaining category.

### Categories & Scoring Rules  

Chance: The player scores the sum of all dice, no matter what they read. For example,  

* 1,1,3,3,6 placed on “chance” scores 14 (1+1+3+3+6) 
* 4,5,5,6,1 placed on “chance” scores 21 (4+5+5+6+1)  

Yatzy: If all dice have the same number, the player scores 50 points. For example,  

* 1,1,1,1,1 placed on “yatzy” scores 50  
* 1,1,1,2,1 placed on “yatzy” scores 0  

Ones, Twos, Threes, Fours, Fives, Sixes: The player scores the sum of the dice that reads one, two, three, four, five or six, respectively. For example,  

* 1,1,2,4,4 placed on “fours” scores 8 (4+4)  
* 2,3,2,5,1 placed on “twos” scores 4 (2+2)   
* 3,3,3,4,5 placed on “ones” scores 0  

Pair: The player scores the sum of the two highest matching dice. For example, when placed on “pair”  
* 3,3,3,4,4 scores 8 (4+4)   
* 1,1,6,2,6 scores 12 (6+6)   
* 3,3,3,4,1 scores 6 (3+3)   
* 3,3,3,3,1 scores 6 (3+3)  

Two pairs: If there are two pairs of dice with the same number, the player scores the sum of these dice. For example, when placed on “two pairs”  
* 1,1,2,3,3 scores 8 (1+1+3+3)   
* 1,1,2,3,4 scores 0  
* 1,1,2,2,2 scores 6 (1+1+2+2)  

Three of a kind: If there are three dice with the same number, the player scores the sum of these dice. For example, when placed on “three of a kind”
* 3,3,3,4,5 scores 9 (3+3+3)   
* 3,3,4,5,6 scores 0  
* 3,3,3,3,1 scores 9 (3+3+3)  

Four of a kind: If there are four dice with the same number, the player scores the sum of these dice. For example, when placed on “four of a kind”
* 2,2,2,2,5 scores 8 (2+2+2+2)   
* 2,2,2,5,5 scores 0  
* 2,2,2,2,2 scores 8 (2+2+2+2)  

Small straight: When placed on “small straight”, if the dice read (1,2,3,4,5), the player scores 15 (the sum of all the dice). 
Large straight: When placed on “large straight”, if the dice read (2,3,4,5,6), the player scores 20 (the sum of all the dice).  

Full house: If the dice are two of a kind and three of a kind, the player scores the sum of all the dice. For example, when placed on “full house”  

* 1,1,2,2,2 scores 8 (1+1+2+2+2) 
* 2,2,3,3,4 scores 0
* 4,4,4,4,4 scores 0

## Chose a task
* Score a given roll in a given category. You do not have to program the full game. No random dice rolling. The computer doesn't have to choose the highest scoring category for a given roll.
  * If you’re short of time, one simplification is to have it always return the sum of the dice, or zero. So the implementation just has to work out if the dice match a category or not.
* Create a working game for a single player.
* Create a working game for human vs human player.
* Create a working game for computer vs human player.

## Extension    
If you’d like to extend the exercise, try adding a requirement to take a given roll, and return a sorted list of all the categories that give a non-zero score for it. Then you’re half-way to an AI that can play the game for you...   

## Additional discussion points for the Retrospective

How much duplication is there in your solution? In your test code?

* Did you write a list of test cases before you started? How did you decide what order to implement them in?  
* If you did this as a refactoring kata, discuss the code smells you identified. Do you have them in your production code?  

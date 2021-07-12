# Master Mind Kata

Mastermind or Master Mind is a code-breaking game for two players. 
The modern game with pegs was invented in 1970 by Mordecai Meirowitz, an Israeli postmaster and telecommunications expert. 
It resembles an earlier pencil and paper game called Bulls and Cows that may date back a century or more. (Source Wikipedia)

## Rules

1. The Mastermind (computer) will select 4 colours. The colours are randomly selected from ["Red", "Blue", "Green", "Orange", "Purple", "Yellow"]. Colours can be duplicated but there will always be exactly 4.
2. The Mastermind will return an array back to you. For every correctly positioned colour in the array an element of “Black” is returned. For every correct colour but in the wrong position an element of “White” will be returned.
3. Passing the correct array will pass the Kata test and return "WON!".
4. Passing an invalid colour will fail the test with the error "Error: you have given an invalid colour!"
5. Passing an invalid array length will fail the test with the error "Error: you must pass 4 colours!"
6. Guessing more than 60 times will fail the test with the error "Error: you have had more than 60 tries!"
7. All colours are capitalised
8. The return array will be shuffled!

## Task

Your task is to create a method called mastermind() that will take an object called game. The object has already been preloaded so you do not need to worry about it.
Within your method you must pass an array into the game object method .check(). This will evoke the object to check your array to see if it is correct.

## Example walkthrough

If the Mastermind selected the following colours

Then the array you are trying to solve is ["Red", "Blue", "Green", "Yellow"]

So you guess with 

["Red", "Orange", "Yellow", "Orange"]

Your method would look like this.

function mastermind(game){
  answer = game.check(["Red", "Orange", "Yellow", "Orange"]);
}
The element 0 => Red is at the correct index so Black is added to the return array. Element 2 => Yellow is in the array but at the wrong index possition so White is added to the return array.

The Mastermind would then return ["Black", "White"] (But not necessarily in that order as the return array is shuffled my the Mastermind).

Keep guessing until you pass the correct solution which will pass the Kata.

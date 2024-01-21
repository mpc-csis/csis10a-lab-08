# Words Of Fortune

In this exercise you get more experience using Strings (which are a type of object in Java).

## Setting up

Use BlueJ to create a new Project called WordOfFortune and then create a new class WordOfFortune. Define the main method as usual.

## Warm up exercises

To prepare for the main part of the lab, practice working with the common String methods by completing the following short exercises at the top of the main method:

```java
   // Setup a Scanner object to read input.
  //   (make sure to import java.util.Scanner;  )
  // Declare a String called secret
  // Ask the user to input a secret word and read it from keyboard
  // print the secret word
  // print how many letters it has
  // print the first letter
  // print the last letter
  // print the secret word in upper case

  // use a traversal loop to print each letter of the word 
  //    separated by hyphens (-)
```

When you have this working, your program should run like this:

```text
Player 1, enter a secret word, from 3 - 10 letters
close
The secret word is close
It has 5 letters
The first letter is c
The last letter is e
In upper case, it is CLOSE
With dashes, it is c-l-o-s-e
```

After the above works, add a line to print a "\f" (erase the screen), and continue with the instructions below.

## Writing the basic game loop

WordOfFortune is a word guessing game. Player 1 inputs a secret word (already done) and Player 2 guesses the word until they get it right. After each guess, the computer will indicate how many letters the guess had in common with the secret word, and other hints. Here is our initial plan:

```java
    // Setup a scanner object to read input.  (done already)
    // Have player 1 input a secret word.     (done already)
    // Declare another String called guess    (start here)
    // Make a do-loop:  
    //   Keep asking Player 2 to type in a guess with the same number of letters as secret 
    //   until they guess the word correctly  (while secret is not the same as guess)
    // Once they guess it right, say so and we're done.
```

When this part works, your program will run like the following:

```text
Player 1, enter a secret word, from 3-10 letters
spider

Player 2, enter a guess, it should have 6 letters
brown
Player 2, enter a guess, it should have 6 letters
bricks
Player 2, enter a guess, it should have 6 letters
spider
You got it! 
```

## Refining the basic loop

Inside your do-loop from the last step, first add an if statement to check that the player's guess has the same number of letters as the secret word, and  print a message if it does not.

Second, create a count variable before the loop starts, and use it in the loop to count how many guesses the user has made. Inside the loop, use an if statement to check the count variable. If they have made 3 or more guesses, and the first letter of secret does not match the first letter of guess, then print the first letter of secret.

Finally, after the loop completes, indicate how many guesses it took to reach the answer. Your program should now run like this:

```text
Player 1, enter a secret word, from 3-10 letters
spider

Player 2, enter a guess, it should have 6 letters
brown
Wrong number of letters!
Player 2, enter a guess, it should have 6 letters
bricks
Player 2, enter a guess, it should have 6 letters
camper
The first letter is s
Player 2, enter a guess, it should have 6 letters
spider
You got it in 4 guesses! 
```

## Providing more feedback

Add a new void method to the program, printCorrectLetters, which takes the secret word and the guess word as arguments and prints out the correct letters, with hyphens (-) in the location of the incorrect letters. This method will contain a traversal loop that examines each letter in guess and compare it with the corresponding letter in secret. If they match, the letter is printed. If they do not match, a hyphen (-) is printed. Here is a hint if you need one.

Test your method by passing secret and guess to it inside the main game loop. Put the call to printCorrectLetters in an else block for the if statement that checks for an incorrect number of letters (this way you will only print correct letters if they both have the same number of letters.)

Now your program should act like this:

```text
Player 1, enter a secret word, from 3-10 letters
camel

Player 2, enter a guess, it should have 5 letters
bricks
wrong number of letters
Player 2, enter a guess, it should have 5 letters
brick
-----
Player 2, enter a guess, it should have 5 letters
bread
-----
The first letter is c
Player 2, enter a guess, it should have 5 letters
craps
c----
Player 2, enter a guess, it should have 5 letters
camps
cam--
Player 2, enter a guess, it should have 5 letters
camel
camel
You got it in 6 guesses!
```

Now that you have it working, erase the secret word at the beginning by printing the "\f" character after it is input.

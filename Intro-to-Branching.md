## If conditions

Introduce the concept of an `if`, which lets us to perform actions only if a certain condition is true. An `if` is always constructed the same way. The condition follows the `if` and is followed by a colon. Note that in Python, the equals sign is not the double equals sign. While the equals sign places code on its right side into the container on its left side, the double equals sign checks the right side against the left. It outputs a boolean ( true / false ). If the boolean output is true, the action indented under the `if` is performed. If it is false, the action will not be performed. 
```python
answer = input( "How many sides does a square have?" )

if answer == "4":
	print "Correct!"
```
> If something is true, then do some code.

> The equals sign differs from the double equals sign! 

> The single equals assigns value and the double checks.


rip from [interactive python](http://interactivepython.org/runestone/default/user/login?_next=/runestone/default/index)

## Else conditions

Next, introduce `else`, which is an alternate condition to `if`. If the `if` condition is false, the action indented under it is bypassed entirely. The next action up for consideration is the one under the `else`. Note that `else` does not have a condition, it is merely the default action when the `if` condition outputs false.
```python
answer = input( "How many sides does a square have?" )

if answer == "4":
	print "Correct!"
else:
	print "Try again."
```
> The action under the else is done when the condition after the if is false.

> Think of the action under the else as the default. 

> Unless the if condition is true, the else action is done.

## Examples

Ask the students to print out their inputted name. Note that `name` is a String, or character sequence.
```python
name = input("What's your name?")
print name
```
> The container name is a sequence of characters, or String type.

Now, ask the students to check if the inputted name is their own. Print a welcome message if it is.
```python
name = input("What's your name?")
if name == "keshav":
  print "Welcome, master!"
```
> Your name must be in quotes following the double equals sign. The quotes make the word keshav a String type. 

> We can only compare the container name with a container of the same type.

Finally, add in the else. Print a warning message when the wrong name is entered.
```python
name = input("What's your name?")
if name == "keshav":
  print "Welcome, master!"
else:
  print "Get off keshav's computer!"
```

## Guessing game

How can we use `if` and `else` to create a guessing game? Introduce the random number generator. Ensure to import the random library and follow the appropriate format for assigning the `randint` class to a container. Note that unlike `range`, the `randint` parameters are inclusive.
```python
import random
answer = random.randint(1, 100)
```
> Note: 1 <= answer <= 100.

Next, ask the students to request an inputted guess and check if the guess is a certain number. Note that the following code is invalid, because `"1"` is not equal to `1`. `guess` is String type. The quotation marks around `"1"` make it also String type. However, `1` is of the integer type and thus cannot be compared to the String `guess` in the `if` condition.
```python
import random
answer = random.randint(1, 100)

guess = input("What's your guess?")

if guess == 1:
  print "You guessed one."
```
> "1" is not equal to 1! Check your container types.

Introduce the `int` function, which changes the inputted container to the integer type. Changing our guess to an integer allows for easy code manipulation and fixes the previous issue in our code.
```python
guess = int(input("What's your guess?"))
```
> We don't need to use quotation marks in our if condition anymore.

> Our guesses are already integer type!

Ask the students to use `if` statements to output whether the guess is too low, too high or correct. Three `if` statements are necessary to accomplish this. Think about the `if` statements as a production line, where `guess` is systematically checked against the randomly produced.
```python
import random
answer = random.randint(1, 100)

guess = int(input("What's your guess?"))

if guess < answer:
  print "You guessed too low"
if guess > answer:
  print "You guessed too high"
if guess == answer:
  print "You guessed correctly."
```
> We use one if statement per each of the three possibilities. 

> The guess can only be less than, greater than or equal to the answer.

> Now we're given one guess per game. How do we add multiple guesses?

How do we repeat actions in Python? Ask the students to initialize a 10-container range. Each container will represent an attempt, so the user gets 10 guesses. Place the game's code within a for loop so that it will be reset each time. This reset allows for multiple guesses!
```python
import random
answer = random.randint(1, 100)
attempts = range(0, 10)

for a in listOfAttempts:
	guess = int(input("What's your guess?"))
	if guess < answer:
		print "You guessed too low"
	if guess > answer:
		print "You guessed too high"
	if guess == answer:
		print "You guessed correctly."
```
> We indent all of our guess / check code inside the loop so we can do them over and over for each guess.

How will we end the game once the correct answer is guessed? Introduce `break`, which ends the program once reached. The `break` is placed under the `if` that checks if guess and answer are the same. If this condition becomes true, the game prints "You guessed correctly." and is then terminated by `break`.
```python
import random
answer = random.randint(1, 100)
listOfAttempts = range(0, 10)

for a in listOfAttempts:
	guess = int(input("What's your guess?"))
	if guess < answer:
		print "You guessed too low"
	if guess > answer:
		print "You guessed too high"
	if guess == answer:
		print "You guessed correctly."
		break
```
> How do we exit the loop and end the game?

> If the correct answer is guessed, the break function ends the game for us.

How do we count the number of tries used? Initialize a new variable `tries` and increment it inside the loop. Each time the user guesses, tries will increase by one. Print the final number of tries at the end of the program. The `str` function converts its input to a String. We convert the integer tries to a String so we may print it in line with the String "Tries taken: ".
```python
import random
answer = random.randint(1, 100)
listOfAttempts = range(0, 10)
tries = 0

for a in listOfAttempts:
	guess = int(input("What's your guess?"))
	tries = tries + 1
	if guess < answer:
		print "You guessed too low"
	if guess > answer:
		print "You guessed too high"
	if guess == answer:
		print "You guessed correctly."
		break

print "Tries taken: " + str(tries)
```
> What is the easiest way to keep track of a total for the number of tries?

> We intialize another container to keep track of the total, the tries variable.

> Tries is of the integer type. 

> Finally, we convert tries to a String type so we can join it with another String before printing.

How would we incorporate more helpful hints into our game? Ask the students to modify their game so it tells you if "you're close" or "kinda close" or "you're way off" to give better hints. Note that they will use the else if, or `elif` ( emphasize the Python syntax ). The action following an `elif` is performed ONLY if the preceeding `if` condition is false.

Changing the game to tell you if "you're close", "kinda close" or "way off".
```python
import random
answer = random.randint(1, 100)
listOfAttempts = range(0, 10)
tries = 0

for a in listOfAttempts:
	guess = int(input("What's your guess?"))
	tries = tries + 1
	if guess < answer:
		if answer - guess > 50:
			print "You guessed way too low."
		elif answer - guess < 10:
			print "You're close, but low!"
		elif 10 <= answer - guess and answer - guess <= 50:
			print "You guessed kinda low."
			
	if guess > answer:
		if guess - answer > 50:
			print "You guessed way too high."
		elif guess - answer < 10:
			print "You're close, but high!"
		elif 10 <= guess - answer and guess - answer <= 50:
			print "You guessed kinda high."
	if guess == answer:
		print "You guessed correctly."
		break

print "Tries taken: " + str(tries)
```
> The else if does its action only if all of the conditions of the preceeding if/elif statements are false.

> Indent carefully! 

> Any action based on an if, else if or else condition should be tabbed under it.

> How do we check how far off our guess is from the answer? Subtraction of the variables!

> Create specific elif conditions that account for a far off answer ( > 50 numbers away ), a semi-close answer ( 10 - 50 numbers away ) and a close answer ( < 10 numbers away ).

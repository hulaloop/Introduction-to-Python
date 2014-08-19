## Splitting a string apart

How can we remove a person's middle name? Ask the students to create a variable `name` and set it equal to their full name, including a middle name. Introduce the `split` function, which chops string type character sequences into parts. The parameter in brackets specifies where to chop. The string is chopped just before the start of the parameter's first character and just after the end of the parameter's last character. Thus, `"keshav muscles saharia"` becomes `'keshav ', ' saharia'` ( emphasize spacing ). 

Removing someone's middle name.
```python
name = "keshav muscles saharia"
name = name.split("muscles")
print name
```
> Notice where the split, or slice occurs. 

> The function slices once before the parameter's start position.

> The function then slices again after the parameter's end position. It yields three separate strings.

## Responding to string input

How do we create a program that replies to text input? Start out by creating an input box. Set the text inputted by the user to a string type variable `answer`. Ask the students to print the inputted answer to check that their input boxes work.
```python
answer = input("Speak, human.")
print answer
```
> The parameter "Speak, human." is the prompt displayed above the input box.

Our eventual goal is to analyze inputted text and respond appropriately. In order to standardize our text, we use the `lower` function. Ask the students to experiment with upper case inputs for `answer` in order to observe the `lower` function in action.
```python
answer = input("Speak, human.")
answer = answer.lower()
print answer
```
> Why do we need to make our inputted answer lower case? This will become clear later in the problem.

How do we split a phrase into words? Create a new string type variable `word` and set it = to the `split` answer without a parameter. Notice the removal of spaces when the new list `answer` is printed after splitting.
```python
answer = input("Speak, human.")
answer = answer.lower()
word = answer.split()
print answer
```
> Without a parameter, the split function removes spaces and isolates words.

> The split function creates a word list from the inputted phrase.

Introduce the idea of checking the list index to read for specific phrases. Create a chain of `if` statements, each one checking the indicies of the list from the 0th ( first ) list position to the 2th ( third ) position. If the correct question is asked, an answer is printed.
```python
answer = input("Speak, human.")
answer = answer.lower()
word = answer.split()

if word[0] == "who":
	if word[1] == "is":
		if word[2] == "this?":
			print "I am Iron Man."
```
> The split function removes spaces but keeps punctuation.

Demonstrate the ability to branch with `if` statements. Indentation can be used to answer different questions starting with "who".
```
answer = input("Speak, human.")
answer = answer.lower()
word = answer.split()

if word[0] == "who":
	if word[1] == "is":
		if word[2] == "this?":
			print "I am Iron Man."
	if word[1] == "made":
		if word[2] == "the":
			if word[3] == "point?"
				print "Michael Jordan."
```
> Can you create several similar questions, each with its own answer? Use branching!

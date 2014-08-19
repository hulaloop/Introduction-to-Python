## Lists of numbers & for loops

Introduce the concept of a list, e.g., list of names of all students in this class, represented in python by a set of values between square brackets. Ask the students to visualize other examples of lists, which can be anywhere from a row of cubbies to a stack of books. Each list consists of indvidual containers, or elements. Initialize `listOfSides` which will range [ 0, 1, 2, 3 ].

The for loop is a construct that repeats over the set of steps contained (or indented) within it. The while loops repeats as the condition for repeating the steps is true. The for loop iterates sequentially over each element in a list. In the while loop `sides` was incremented by 1 each run. In the for loop, the hidden counter auto increments during each run. The counter ensures that the loop runs as many times as there are elements in the list.

Another way to think about the first line of the for loop is that a new variable `s` is initialized to the value of the first list element. This variable increments to the next element in the next loop run. Think of it as the variable in your while loop condition that you have to manually increment each loop run, except that the for loop does the incrementing for you.
```python
listOfSides = [ 0, 1, 2, 3 ]

for s in listOfSides:
	alex.forward(100)
	alex.left(90)
```
> listOfSides is a variable that is the entire list of values [ 0, 1, 2, 3 ].

> The variable s represents the side alex is drawing during each run. When s = 2, alex is drawing the third side.

> While loops need a counting variable to add to at the end of each run. 

> For loops auto add to the hidden counter each run. The hidden counter runs the loop as many times as there are elements in the list.


## Lists of colors & for loops

Ask the students to draw a square using a list of colors. This problem demonstrates the concept that `alex` cycles through each value in the list one by one to draw each corresponding side of the square. This problem also shows that there are lists with Strings (words) and variable types other than integers (numbers).

Initialize `listOfColors` and fill it with four color names in brackets. Create a for loop with the first indented line within the loop changing the turtle's color before each side of the square is drawn. Add the rest of the draw code and once again bring the students' attention to the correspondence between the multicolored square's sides to the order of colors in the original list.

In order to further elucidate the idea, have the students now call their list `c` and their newly initialized variable `listOfColors`. Ask them if they think the code will run. After receiving a response, go ahead and run the code. Reinforce the concept that the names of the list and the variable that runs through the list are less relevant than the idea that the newly initialized variable is independent of the list. The context that the name is presented in is far more important in determining what the variable refers to than the name itself.

```python
listOfColors = [ "red", "green", "orange", "blue" ]

for c in listOfColors:
	alex.color(c)
	alex.forward(100)
	alex.left(90)
```
> How can we draw a multicolored square?

> Picture how changing alex's color before drawing each side will affect the square. Remember the color function?

> We first used a list of numbers to draw sides, but we can also use a list of colors. 

> The parameters are words in "" marks instead of numbers, but the idea of a four element list is the same.


## Range function

Ask the students to consider how they would create a list if the list consisted many numbers, e.g. the list of all numbers between 1 and 200. It is impractical to type out each list element, so how can we make it easier? Introduce the range function, displayed as range(a, b) where a is the starting number and b is the final number + 1 (be sure to highlight that b is NOT the last number in the range).

Drawing a pentagon using the `range` function:
```python
listOfSides = range(0, 5)

for s in listOfSides:
	alex.forward(100)
	alex.left(72)
```

> Notice that instead of typing out a list [ 0, 1, 2, 3, 4 ], we can replace it entirely with the range function.

## Nested for loop

Ask the students to consider the previous color & spiral problems. Inquire how they would draw an expanding multi-colored spiral as created by the code below. Guide them to recognize the similarities to their previous programs, namely increasing the length moved and changing the color before each line is drawn.

Explain that the only way to draw individual squares of equal sides that increase in size as they stack is to run through all four colors in a color list for each iteration of a larger number list. This scenario is known as a nested for loop, formed by placing a for loop inside a for loop. We add in the last line of code outside the inner loop but inside the outer loop in order to provided the offset between squares of increasing size.

Draw a simple nested for loop on the board. Walk the students through both loops so that they truly understand that for each single iteration of the outer loop, the inner loop runs through the entire range.

```python
listOfNumbers = range(10, 150, 3)
listOfColors = [ "red", "blue", "orange", "green" ]

for n in listOfNumbers:
	for c in listOfColors:
		alex.color(c)
		alex.forward(n)
		alex.left(90)
	alex.right(8)
```
> Each square has sides of equal length. 

> We use the colors list to draw each multicolored square.

> The size of the squares increases as they stack. 

> We use the numbers list to move alex by a bigger amount during each run, drawing a bigger square each time.

> The last parameter in the list, or range is the distance between each number in the range.

> The list of colors must run four times for each run of the list of numbers. This stacks larger multicolored squares.

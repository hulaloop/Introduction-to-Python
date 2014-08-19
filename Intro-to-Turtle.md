# Shapes

In this lesson, students will use the `turtle` module to familiarize themselves with the basic syntax of Python. Students who have had some experience with programming will pick up the content of this lesson very fast, so it is advisable to have them work on the [advanced problems](#advanced-topics).

![first day](http://pythonroom.com/img/screen1.png)

## Prior Knowledge

No prior knowledge.

## Objectives
 - [Objects](../concept/objects.md)
 - [Functions](../concept/functions.md)
 - [Code Blocks](../concept/code-block.md)

## Creating a turtle

Students start off with two lines of code. The first line imports the `turtle` library, and the second line uses the `Turtle` function of the turtle library to create a turtle object and store it in the variable `t`. When starting off, it is best to give a very brief explanation what these two lines do, and elaborate more on them later in the lessons on modules and functions.

```python
import turtle
t = turtle.Turtle()
```
> To start off, we gave you two lines of code. The first line, import turtle, pulls in a bunch of pre-built Python code that we can use in our program. The second line, turtle.Turtle(), creates a virtual turtle and stores it in the variable t.

It's important to point out here that variables in programming work the same as variables in a math class, but variables in programming can store much more than just numbers. In this case, the variable `t` is storing a virtual turtle.

## Variable names

The variable name `t` is not very descriptive, so we'll start the lesson by changing it. This gives students an idea of what an acceptable variable name can be, namely that a variable name must

  * have no spaces
  * start with a letter
  * have no punctuation characters (`,`, `.`, `:`, `;`, `#`, ...), except for the underscore (`_`)

It's also worth pointing out that a variable name can

  * contain numbers, as long as the number is not the first character of the name
  * use camel case for multiple words (longVariableNameExample)

Students should name their turtle something unique - in my example, I'll name my turtle alex.
```python
import turtle
alex = turtle.Turtle()
```

It's important that the instructor give a quick primer on variables so students understand that the word `alex` is just a way of referring to a turtle.
> A variable is a container for information. In order to put different information into a variable, or take information out, we need to be able to refer to it with a unique name. The name we use has some restrictions - it can't have spaces or punctuation characters. It can contain numbers, but it must start with a letter.

It's also worth pointing out how the assignment operator `=` works. It takes the value on the right side (the turtle created by `turtle.Turtle()`), and puts it into the variable on the left side.
> Text on the right side of the equals side is stored in the container on the left.

Later, when students want to refer to the turtle they just created, they will have to use the same name (in my case, it is `alex`).
> Going forward, our turtle will be called alex.

## Calling functions

You can now tell the turtle to perform certain actions. For example, you can tell the turtle to move forward.
```python
alex.forward(100)
```

Let's quickly dissect this command. The first part, `alex.`, is telling the turtle stored in the `alex` variable to perform a certain action. The period operator (`.`) is like the command "do" - it tells the *object* on the left to do the action on the right. We'll look more closely at objects later - for now, think of them as a virtual representation of a physical thing.

The action, ```forward```, needs to be *quantified*. Imagine if you were on a sports team, and your coach looks at you and yells "RUN!". The coach has only told you an action, but you need some more information before you can act on it. Where do I run to? How far do I run? How fast?

In Python, any action (technically referred to as a *function*) needs to have some additional information (technically referred to as *parameters* or *inputs*) in order to run. That's why, after the action, we provide a list of inputs within the parentheses.

So in general, the actions look like
```
thing . action ( ... inputs ... )
  1   2    3   4        5       6
```
1. The variable storing whatever is performing the action
2. The dot operator, equivalent to the "do" command
3. The name of the action
4. The opening parentheses
5. A list of inputs (if there is more than 1 input, separate with a comma)
6. A closing parentheses

> A function will tell alex to do an action.

```
Alex goes forward. Translates to:
   |  |   |
   v  v   v
  alex.forward
```

> The noun is 'alex', the verb is '.' and the adjective is 'forward'.

> A parameter is an input to a function. It is found in the parentheses following a function.

> Alex knows to go forward, but how far should he go?

> If we want alex to go forward 100 pixels, 100 is the parameter in the parentheses. So, to make alex go forward 100 spaces we write alex.forward(100).


## Basic turtle functions

The turtle has several functions that it can do. It is important to tell students that the function names are predefined, and that they can't just make up a function like ```turtle.dance("boogie")```. 

Here are the basic functions that they should know right now:
```python
alex.forward( pixels )
alex.backward( pixels )
alex.left( degrees )
alex.right( degrees )
```

Changing the turtle's direction.
```python
alex.forward(100)
alex.left(90)
```

> The forward/backward functions tell alex to move, but what tells alex to turn?

> The left/right functions will tell alex to face a different direction. The parameter is the degrees that Alex turns.

## Drawing a square

Suppose you want your turtle to draw a square. This is a larger, more abstract goal, and the job of a programmer is to reduce it to a list of simple steps.

When in doubt, *be the turtle*. This is student-friendly vernacular for thinking from the perspective of the turtle, which involves visualizing where the turtle is and what direction it is pointing at any point in the process being described. Since future lessons will involve a significant level of visualization, it is ideal to get students started early. 

```python
alex.forward(100)
alex.left(90)
alex.forward(100)
alex.left(90)
alex.forward(100)
alex.left(90)
alex.forward(100)
alex.left(90)
```

> Using the functions we know, how will we draw a square?


## More functions

Change the color.
```python
alex.color("red")
```

> Right now, alex moves in black lines. How do we change line color?

> The color function lets us change line color. We place quotation marks around parameters that are words, not numbers. So, the names of colors are written in quotes. 

> This function will change alex's (and his line's) color to red.

Will draw a line as it moves to a certain coordinate.
```python
alex.goto( x, y )
```
> Right now, the turtle window is a coordinate plane with its center being (0, 0). Alex starts off at the origin.

> To move alex to a specific coordinate, we use the goto() function. The parameters are ( x, y ) coordinates that tell alex where to move to. 

> Note that the goto() function causes alex to draw a line as he moves.

Will not draw a line as it moves to a certain square (teleportation).
```python
alex.setpos( x, y )
```
> The parameters are ( x, y ) coordinates that tell alex where to move to from the origin.

> Note that the setpos() function works like goto() but without the line being drawn.

Sets the direction of the turtle to the corresponding angle measure.
```python
alex.setheading( angle )
```
> alex starts out facing right.

> The parameter of setheading() is the measure of the angle alex will turn from his initial direction.

Stamps the image of the turtle on wherever the turtle is located
```python
alex.stamp()
```
> Leaves behind a still image of alex at his current location, even as alex proceeds.

## Variable substitution

As progammers we strive to optimize our code whenever possible. If we replace the number of pixels we go forward with a variable `distance` we can manipulate the size of our shape with ease. If we replace the degrees turned with `angle` we can easily manipulate the angles and subsequently the shape drawn. Ask the students to double `distance` and observe the effect it has on the square's size.

```python
distance = 100
angle = 90

alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
```

> Up until now, we have given individual values to each parameter. How can we make this more efficient? 

> Parameters can also be other variables.

> We will create two new variables, distance and angle. Each has a specific value. We will replace our previous parameters with distance and angle.

> So, distance = 100 and angle = 90. Use of variables makes it easy to change our code. For example, If we wanted to double the square's size, we would simply double the value of distance to 200.

## Drawing a pentagon

Ask the students which parameters must change when drawing a five-sided pentagon instead of a four-sided square. The angle is set to 72 degrees and another forward and left functions are added to complete the fifth side.

```python
distance = 100
angle = 72

alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
```
> What parameters need to change if we wanted to draw a pentagon instead of a square?

> If we keep the angle at 90, we only re-draw the square. So, the angle has to change!

> After changing the angle to 72, we notice one side still missing. So, we need to repeat the forward and left function once more.

## Using the Interior Angle Formula

Start off by introducing the Interior Angle Formula, which is used to determine the interior angle of a polygon from its number of sides. Give the students the following formula:
```
                                         360
Interior Angle of a Polygon (n-sided) = -----
                                          n
```
Create a variable `sides` to represent the number of sides of the polygon. Set `angle` equal to the Interior Angle Formula. Ask the students to experiment with changing the number of sides and adding the appropriate number of forward & left functions to the copy+pasted code. Note the increased efficiency of drawing polygons of various sizes.

```python
sides = 5
distance = 100
angle = 360 / sides

alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
```

> Right now, we have to change the sides and the angle in order to different shapes.

> To make it easier, we create a new variable for the number of sides of the shape.

> We then change our angle variable to equal the formula for the each angle inside a shape.

> Try drawing shapes with different numbers of sides.


## Deriving the Interior Angle Formula

Ask the students to draw out three polygons, each with a different number of sides. Instruct them to draw as many non-overlapping triangles as possible within each. Notice that if a polygon has n sides, n - 2 triangles can be drawn.

The interior angles of a triangle sum to 180, so we will multiply ( n - 2 ) * 180 to obtain the total of all the angles in a polygon. Dividing this result by the number of sides ( which equal the number of angles ) will yield the interior angle of the given polygon.

Draw a right-facing alex on the board. Demonstrate that in order for alex to turn at an interior angle, he must go left from his current position by ( 180 - Interior Angle ). Draw alex, his path and highlight the angle he must turn at in order to illustrate this principle.

Our Interior Angle is equal to ( n - 2 ) * 180 / n, so the amount alex turns is 180 - ( n - 2 ) * 180 / n. Note that this formula can be simplified to our original Interior Angle Formula, 360 / n.

```
                                                ( n - 2 ) * 180
Interior Angle of a Polygon (n-sided) = 180 -  -----------------
                                                       n
```
> Each polygon has n sides. How many triangles can we draw in each one (in terms of n)?

> To find the total angles inside the polygon, multiply number of triangles ( n - 2 ) by the sum of a triangle's angles (180 degrees).

> How will we find the measure of each Interior Angle using the total angles? Divide by number of Interior Angles!

> The number of Interior Angles matches the number of sides (n).

> Picture how much alex turns from his start direction at each Interior Angle. If we draw how he turns we see that he turns by ( 180 - Interior Angle ).


Drawing a pentagon using the derived Interior Angle Formula.
```python
sides = 5
distance = 100
angle = 180 - ( n - 2 ) * 180 / n

alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
alex.forward(distance)
alex.left(angle)
```

> 360 / n rounds the angle to the nearest whole number. So, the derived Interior Angle Formula is more accurate!


## While loop

We will now draw the square with a while loop. Ask the students to explain how the original copy+pasted code draws their square. 

We will build each side of the square iteratively, repeating the steps for building each side as many steps as needed. In this case we repeat the steps four times, one for each side. Thus, we will intialize `sides` beginning at 1.

The while loop is a construct that iterates through the steps indented below the construct while the given condition remains true. In this case, the condition runs the loop as long as `sides` < 5, drawing four sides. Each repetition of steps is a 'run'. Ensure to increment `sides` by 1 at the end of each run before compiling to avoid infinite loops and program crashes.

```python
sides = 1

while ( sides < 5 ):
  alex.forward(100)
  alex.left(90)
  sides = sides + 1
```

> How did we draw a square with the copy+pasted code?

> The variable for sides is now the number of sides of the square. We start sides at 1 and we add 1 to it after each side alex draws.

> The while loop only repeats as long as the counter sides < 5. This is because a square has four sides.

> The text indented under the loop is repeated during each repeat.

> If we forget to increase sides by 1 each time the while condition is always true. An infinite loop results!

> Infinite loops can make you lose code. Avoid at all costs!

In general, ensure that students are avoiding infinite loops, as they can cause pythonroom to crash. For younger students, it is recommend to avoid loops until they are more comfortable with the Python syntax.

## Advanced topics

For students who get it faster, some advanced topics:

- Try drawing the first letter of your name

- Try drawing a outward spiral and look for a pattern in the numbers.

```python
t.forward(5)
t.left(5)
t.forward(10)
t.left(10)
t.forward(15)
t.left(15)
...
```






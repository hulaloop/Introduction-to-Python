# Koch snowflake

```python
import turtle
t=turtle.Turtle()
t.setpos(-120, 140)
t.speed(0)
t.hideturtle()

def koch(length):
	if length<5:
		t.forward(length)
		t.left(60)
		t.forward(length)
		t.right(120)
		t.forward(length)
		t.left(60)
		t.forward(length)
	else:
		koch(length/2)
		t.left(60)
		koch(length/2)
		t.right(120)
		koch(length/2)
		t.left(60)
		koch(length/2)
			
for x in range(1, 51):
	koch(24.0)
	t.right(90)
```

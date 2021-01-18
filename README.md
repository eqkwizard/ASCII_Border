# ASCII_Border
Create a function that takes a shape (set of unit squares) and returns the borders of the shape as a multiline string (using '+','-','|').

Input
shape [set of tuples (int, int)]
The shape is a plane geometric figure formed by joining one or more unit squares edge to edge or corner to corner. The shape parameter contains the (x,y) coordinates of the unit squares that form the shape.

x axis is horizontal and oriented to the right, y axis is vertical and oriented upwards.

Examples
A set with one element (e.g. {(1,1)}, {(7,11)} or {(50,35)}) represents a square whose sides have length 1.
A set with two elements with the same y coord and consecutive x coord (e.g. {(1,1),(2,1)} or {(7,5),(8,5)}) is a rectangle, width: 2, height: 1. A set with two elements with the same x coord and consecutive y coord (e.g. {(1,1),(1,2)} or {(7,5),(7,6)}) is a rectangle, width: 1, height: 2.

Ranges
Size of shape (len(shape), number of unit squares): 1–1500
Width/height of shape (max(coord)-min(coord)+1): 1–90
x, y coordinates: -100–100
Output [string]
Multiline string representing the border of the input shape, using '+' (corners), '-', '|' (edges), ' ' and '\n'.

No trailing spaces
No trailing newline
Minimum leading spaces (at least one line starts with a non-space char)
Border drawing
There is a 1:1 relationship between chars in output string and unit squares in input shape. Borders are drawn immediately outside the shape, in the squares that have an edge or a corner in common with the shape.

The shape may have holes. Holes must be ignored.

Examples
1x1 square => 3 rows, 3 chars per row; a central space (the shape) surrounded by border chars:
{(1,1)}  =>  '+-+\n| |\n+-+'
+-+
| |
+-+
2x1 rectangle => two adjacent spaces surrounded by border chars
{(1,1),(2,1)}  =>  '+--+\n|  |\n+--+'
+--+
|  |
+--+
1x2 rectangle
{(1,1),(1,2)}  =>  '+-+\n| |\n| |\n+-+'
+-+
| |
| |
+-+
4x4 square with a 2x2 hole => only outer borders are drawn, hole is ignored:
{(0,0),(0,1),(0,2),(0,3),(1,0),(1,3),(2,0),(2,3),(3,0),(3,1),(3,2),(3,3)}  =>  '+----+\n|    |\n|    |\n|    |\n|    |\n+----+'
+----+
|    |
|    |
|    |
|    |
+----+
Test constraints
There are 150 tests:

23 fixed tests, with small shapes (1–45 unit suares)
32 small random tests (~ 25–45 unit squares)
45 medium random tests (~ 140–360 unit squares)
50 large random tests (~ 350–1000 unit squares)

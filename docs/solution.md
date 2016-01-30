# Max Rectangle Algorithm Solution
I will describe three ways to solve this problem.

## My Assumptions:
For all the algorithms that are presented here I offer to do the following pre-processing actions:

1. Since we are interested and affected only by what happens inside the container, we will trim all the rectangles that are fully or partially located outside the container:

2. Personally I prefer working where the container always starts at (0,0). This is acheived simply by shifting the container and the rectangles in the X and Y axises and shiting back the result.

3. I will mark the container coordinates with (Xcl, Xcr, Yct, Ycb) where the first letter is the axis, the seconds is 'c' for container and the last one is the dirction ('l'-left, 'r'-right, 't'-top, 'b'-bottom).

Note that actions 1 and 2 have O(n) complexity. 

## Solution 1: Grid-Based Brute Force 
### Overview
We will scan all the cell of the container and we will check for each cell what will be the biggest possible rectangle

### Description of Algorithm:
Divide the container into a cells of size 1x1
Mark the maximum rectangle as size 0
For each cell:
- For all the rows staring from the row of the current cell and ending in the last row of the container
- - Iterate from the cell X position to the container right edge
- - If encountered a rectangle or the edge check new max and store coordinations

### A More Mathematical Definition

```javascript
Divide the container into a cells of size 1x1. (This could simply acheivied by using two-dimentional array)

mark max-rec as size 0
for each cell (Xi, Yj) of the container:

// Check that the current cell is not inside any other rectangle
If cell (Xi, Yj) is inside a rectangle, continue to the next cell

// For all the lines from the current cell to the edge of the container
for every line Yk from Yj to Ycb:
  // For every cell in the current row starting with the current cell x location
  mark max_length = MAX_INTEGER
  for every cell (Xm, Yk) from (Xi, Yk) to (Xcr, Yk)
  
  // Check that the next cell is not inside a rectangle
  If cell (Xm+1, Yk) is inside a rectangle OR (m-i < max_legth)
  
  // We reached a cell that is inside a rectange; 
  // Check if we encountered a new rectangle
  if rectangle(Xi, Yj)-(Xm, Yk) > max-rec save it as max-rec
  mark max_length = m-i
  
The maximum rectangle is in max-rec
```

The complexity of this algorithm is O( (w*h)^2 ) where 'w' and 'h' are the width and height of the container.
This algorithm can be considered as acceptable solution where m << n and h << m

## Solution 2: Improved Brute Force
### Overview
We will build a 'smart' grid where we will extend all the edges of all the rectangles until they intersect with the container edges.
For each generated point we will find the maximum rectangle where the point is the upper-left coordinate

The following image illustrates the 'smart' grid (extended lines marked in gray)
![Image of Problem](../images/bf2-1.png)

### Description of Algorithm:
Build a vector of all the horizontal edges.
Build a vector of all the vertical edges.

For every horizontal edge build the extended edge and add all the intercepting vertical edges (create the 'virtual' points)

Go over all the horizontal edges and for each edge:
Add the two edge points to the list of points
build the extended edge (the 'l' will be 0 and the 'r' will be the containers' 'r')
add all intersecting points of the current extended edge with the previously processed edge to the list of points

// Find the largest possible rectangle the the next point is it's upper-left corner
For each point in the list of points:
* For all the points on the same edge with higer Y coordinates value
* Start with the X axis of the point





### A More Mathematical Definition


## Solution 3: The Real Solution
### Overview
This algorithm based on vertical swift of the lower edges of the rectangles until encountering a top edge or part of it.

We have two pre-processing actions:
1. For all the horizontal lower edges calculate the extended edge (extend the edge on both directions of the x-axis until encountering a rectangle or the container edge.
![Image of breaking edge to visible parts](../images/algorithm3-2.png)
2. For all vertical rectangles, break the rectangle for the visible parts of a rectangle
![Image of breaking edge to visible parts](../images/algorithm3-1.png)
### Description of Algorithm:

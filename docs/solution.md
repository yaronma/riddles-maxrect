# Max Rectangle Algorithm Solution
I will describe three ways to solve this problem.

## My Assumptions:
For all the algorithms that are presented here I offer to do the following pre-processing actions:

1. Since we are interested and affected only by what happens inside the container, we will trim all the rectangles that are fully or partially located outside the container:

2. Personally I prefer working where the container always starts at (0,0). This is acheived simply by shifting the container and the rectangles in the X and Y axises and shiting back the result.

3. I will mark the container coordinates with (Xcl, Xcr, Yct, Ycb) where the first letter is the axis, the seconds is 'c' for container and the last one is the dirction ('l'-left, 'r'-right, 't'-top, 'b'-bottom).

Note that actions 1 and 2 have O(n) complexity. 

## Solution 1: Brute Force (^2) - 
### Description:
Divide the container into a cells of size 1x1
Mark the maximum rectangle as size 0
For each cell:
- For all the rows staring from the row of the current cell and ending in the last row of the container
- - Iterate from the cell X position to the container right edge
- - If encountered a rectangle or the edge check new max and store coordinations

### A More Mathematical Definition

Divide the container into a cells of size 1x1. (This could simply acheivied by using two-dimentional array)

mark max-rec as size 0
for each cell (Xi, Yj) of the container:

// Check that the current cell is not inside any other rectangle
If cell (Xi, Yj) is inside a rectangle, continue to the next cell

// For all the lines from the current cell to the edge of the container
for every line Yk from Yj to Ycb:
  // For every cell in the current row starting with the current cell x location
  mark max_length = MAX_INTEGER
  for every cell (Yk,Xm) from (Yk,Xi) to (Yk, Xcr)
  
  // Check that the next cell is not inside a rectangle
  If cell (Yk, Xm+1) is inside a rectangle OR (m-i > max_legth)
  
  // We reached a cell that is inside a rectange; 
  // Check if we encountered a new rectangle
  if rectangle(Xi, Yj)-(Xm, Yk) > max-rec save it as max-rec
  mark max_length = m-i
  
The maximum rectangle is in max-rec
  
  
  
  
  




## Solution 2: Improved Brute Force

## Solution 3: The Real Solution

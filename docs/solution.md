# Max Rectangle Algorithm Solution
I will describe three ways to solve this problem.

## My Assumptions:
For all the algorithms that are presented here I offer to do the following pre-processing actions:

1. Since we are interested and affected only by what happens inside the container, we will trim all the rectangles that are fully or partially located outside the container:

2. Personally I prefer working where the container always starts at (0,0). This is acheived simply by shifting the container and the rectangles in the X and Y axises and shiting back the result.

3. I will mark the container coordinates with (Xcl, Xcr, Yct, Ycb) where the first letter is the axis, the seconds is 'c' for container and the last one is the dirction ('l'-left, 'r'-right, 't'-top, 'b'-bottom).

Note that actions 1 and 2 have O(n) complexity. 

## Solution 1: Brute Force (^2)
Divide the container into a cells of size 1x1.

for each cell of the container we will find the largest rectangle:
- I assumt the cell is located at (Xi, Yj)
- If the cell is inside any other rectangle skip to the next cell (O(n*log(n)). [I will post a seperate description of this algorithm]
- Scan line Yj starting with Xi+1 and ending in Xcr





## Solution 2: Improved Brute Force

## Solution 3: The Real Solution

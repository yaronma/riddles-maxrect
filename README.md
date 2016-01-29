# Max Rectangle Algorithm
Calculate the max rectangle that can be inserted into container rectangle with embedded rectangles

## The Problem:
Given a container rectangle (I will simply call it "container") and a set of rectangles we need to calculate the maximum rectangle that we can add to the container without intersecting the container or any embedded rectangles.

The following image illustrates the problem:

#### Remarks:
- We use the Y-inverted axis system where the upper-left corner is marked as 0,0 and x is growing while moving to the left and y is growing while moving down.
- The rectangles (including the container) are expressed as 4 integers Rect=(l, r, t, b) 
where: 
l is the left x coordinate
r is the right x coordinate
t is the top y coordinate
b is the bottom y coordinate

- Each rectangle can be placed anywhere (even with negative coordinates)
- The rectangles can be place inside or outside or intersecting each other (and the container)

## The Target:
After placing the container and all the rectangles, find the maximum possible rectangle that can be placed with in the container while not intersecting any of the rectangles (it may touch the other rectangles)

# The Solution
[Press here for the solution!](docs/solution.md)

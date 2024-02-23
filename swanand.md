
 ## **Problem Statement :**
Swanand is on a difficult trek through the Himalayas, where it is difficult to find his way back to a starting point.

He follows 2 strategies while trekking:

1) He decided to only move up from each point and return when doesn’t have the next higher point. (While returning he comes back to his original location and goes for the next trek path)

2) As Swanand knows the fact that from the room he can go east, west, south, and north but after that, he decided to go nearest higher height only, and at any point, he finds the same height then he follows "north-south-east-west" while making the choice.

At each location, he notes the height in the NxN matrix so he can easily determine which direction to go.

Your task is to find all the paths that Swanand takes during his journey.

**Input Format :**
#### **<u>Input Format</u>**

The first line contains the size of the trek Swanand plans to do.

The second line has two integers (i, j) representing Swanand’s original position.

The following N lines contain the description of the trek.

The following N lines each contain n integers representing the heights of each point.

#### **<u>Output Description</u>**

Output all trek paths in the "north-south-east-west" order. if no path for a particular direction, then print "-1".


### Difficulty:

Medium

### Prerequisite:


Backtracking,recursion


# Detailed Explanation:

Swanand's trek through the Himalayas involves making choices at each point based on certain conditions, creating a branching path. Let's break down the problem-solving approach using depth-first search (DFS) and recursion.




## Problem-Solving Approach:

### 1. Recursive Function (DFS):

- Define a recursive function `trekPaths` that explores different paths based on the defined strategies.
- Check conditions for valid moves, updating the path and current position accordingly.
- If the current position reaches the original location, return the current path.
- Explore all possible paths recursively.

### 2. Direction Decision Function:

- Define a function `findDirection` to determine the next position based on the nearest higher height.

### 3. Main Function:

- Read input values and initialize the matrix.
- Call the `trekPaths` function for each direction (north, south, east, west) from the starting position.
- Print the paths obtained.

## Pseudo Code:

```cpp
function trekPaths(n, matrix, px, py, prev, path):
    if px < 0 or py < 0 or px >= n or py >= n or matrix[px][py] <= prev:
        return -1
    
    path += matrix[px][py] + " "
    curr_position = findDirection(n, matrix, px, py, matrix[px][py])

    if curr_position[0] == px and curr_position[1] == py:
        return path

    return trekPaths(n, matrix, curr_position[0], curr_position[1], matrix[px][py], path)

function findDirection(n, matrix, px, py, prev):
    curr_position = [px, py]
    min_height = 1000

    // Check for the nearest higher height in all directions
    // Update curr_position accordingly

    return curr_position

function runProgram(input):
    // Read input and initialize matrix
    // Call trekPaths function for each direction
    // Print the obtained paths

// Execute runProgram with sample input



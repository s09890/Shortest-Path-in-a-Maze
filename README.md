[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Lj_y2y4Z)
# Find Shortest Paths of Maze

## Due 04/27 at 11:59pm


Learning Goals
==============

* Understand how to traverse a maze

Find Shortest Paths in a Maze
=============================

This assignment gives a map of a maze. The map is a rectangle of
"cells" (or grids). Each cell is either a wall (expressed by `b` as
brick) or a passage way (expressed by space ` `). This assignment asks
you to write a program that marks *every* reachable cell by the
**shortest distance** from the starting point (expressed by `s`).

Algorithm to Find Shortest Paths
================================

Please design your own algorithm to find the shortest path. To
encourage you to think of an algorithm, this assignment does not
specify the algorithm you need to use.

Two common used algorithms are *depth first with back tracking* and
*breadth first*. From the starting point, mark it zero

- If a cell is open, visit that cell, keep going as far as
  possible. Add one to the distance whenever moving to the next
  cell. When it is no longer possible moving forward, **go back to the
  last intersection and take a different direction**. If a cell is
  visited the multiple times, keep the shortest distance. Hint: use
  the call stack to store which cells have been visited and the
  distances to the starting point.

- Mark all reachable cells the same distance (this cell's distance +
  1). Store these cells in a list.  Pick one from the list and
  continue until no cell is added.


Maze Generator
==============

This assignment uses the maze generator from "Killer Game Programming
in Java" by Andrew Davison, O'Reilly, May 2005. The original program
is provided (unchanged) in the MazeGen/ directory.

This assignment makes a few minor changes to the maze generated by the
original maze generator:

* replace 'c' by 'b'
* remove the empty lines at the top, bottom, left, and right
* (randomly) remove a few bricks so that some mazes have multiple paths from
  the source to the exit

Assumptions about Valid Mazes
=============================

A valid maze should meet the following conditions. Only valid mazes
are used for testing your program. Your program does not have to check
whether an input maze is valid or not.

* There is one and only one exit at a space (` `) on the top row.

* The maze is fully enclosed by bricks, except the only exit. 

* The starting point is marked one and only one `s`.

* It is possible that some cells are not reachable. It is also
  possible that some cells may be reached by different routes.

Your Program's Input
====================

You program will take 1 argument as input:

* `argv[1]` is the name of the input file

Output Format
=============

Output should be printed to `stdout` with `printf()`. Your output should match the ones in the expected files. Some key notes:

* Walls should have value -1
* Start should have value 0, as it requires 0 steps to get to that
  location
* Open spaces that aren't reachable should have value `width * height + 1`, which is
  the theoretical maximum amount of steps



Submission
==========



For this assignment, you need to provide all necessary files **and**
`Makefile`.  Your program will be tested using the following commands

`make`: generate an executable called `hw19`. Please remember that the
executable must be called `hw19`. Any other name will be rejected.

If `make` fails, you will receive no score in this assignment. Each
warning message has 10% penalty of the score.

When you are ready to submit your code for grading, you need to *tag* the version you want us to grade. A tag is a way of assigning a name to a particular version of code. We look for the tag `final_ver` to decide what to grade.

1. Tag your local code: `> git tag final_ver`
2. Push the tag to GitHub: `> git push origin final_ver`

If you later decide you want to update the version you submit, you can tag a different version:

1. Update the tag: `> git tag final_ver -f`
2. Push the tag to GitHub: `git push origin final_ver -f`

We will grade whichever version has the `final_ver` tag at the due date.

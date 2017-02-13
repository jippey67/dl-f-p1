# Solve a Soduku with AI

This repository contains the work I did for the Soduko project in the Artificial Intelligence Nanodegree. There are two parts to the project: implementation of the naked-twins search and modify technique, and implementation of the extension of the sudoku rules to include the diagonal constraints. I'll go over both parts in the following paragraphs.

## Sudoku rules

A Sudoku is a puzzle usually containing 81 cells in a 9x9 grid, subdivided in 9 3x3 grids. Each cell can contain one of the numbers ranging between 1 and 9. A couple of cells filled-out already form the starting point of the sudoku. Solving the sudoko requires following the constraints that:
* in a single row each number needs to be present (and thus no number can occur more than once)
* in a single column each number needs to be present
* in each 3x3 grid each number needs to be present
With these constraints the objective is to put a number in each square.

The set of all rows, columns and 3x3 grids will be called 'units' in the remainder of this article.

## Naked twins in a Sudoku

Naked twins in a Sudoku occur when within a unit 2 cells can only contain the same 2 values. As for these cells 2 values must be chosen out of a set of 2, those numbers cannot occur elsewhere in the same unit. They can therefor be stripped from the possibilities of all other cells in the unit. There are basically two approaches possible to implement this within the setup prepared in the Python files: 

Search the Sudoku for a cell containing 2 digits --> search it's peers for a cell containing the same digits --> find units where both the first cell and the peer belong to --> remove the twin digits from all other cells in the units.
As this approach requires both searching the peers and the units it is ineffcient and I therefore chose approach two:

For each unit find the cells containing 2 digits --> find twins within this set --> remove the values in the twin from all other cells in the unit.

## 

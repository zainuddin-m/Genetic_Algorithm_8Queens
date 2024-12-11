# Genetic Algorithm for 8-Queens Problem

This repository contains an implementation of a Genetic Algorithm (GA) to solve the **8-Queens Problem** using Python. The goal of the 8-Queens Problem is to place 8 queens on a chessboard so that no two queens threaten each other.

---

## **Features**
- **Encoding Scheme**: A permutation of numbers 0–7, where each number represents the row position of a queen in the corresponding column.
- **Fitness Function**: Calculates the number of diagonal conflicts between queens.
- **Genetic Operators**:
  - **Selection**: Tournament selection to favour fitter solutions.
  - **Crossover**: Order Crossover (OX) to combine valid parent permutations.
  - **Mutation**: Swap mutation to shuffle queen positions.

---

## **Dependencies**
The following Python libraries are required:
- **numpy**: For mathematical operations.
- **DEAP**: A framework for evolutionary algorithms.
- **matplotlib**: For visualising the chessboard.

Install dependencies using:
pip install deap numpy matplotlib

## **How It Works**
Initialization: Generate a population of random permutations for queen positions.

Fitness Evaluation: Count the number of diagonal conflicts for each solution.

Selection: Use tournament selection to choose the best solutions for reproduction.

Crossover and Mutation: Combine and mutate solutions to explore new possibilities.

Evolution: Iterate over generations to improve the population.

Output: The algorithm outputs a conflict-free solution and a visualisation of the chessboard.

## Results
The genetic algorithm successfully finds a solution with no queens attacking each other.

A visualisation of the chessboard is provided, showing the valid placement of queens.

## Code Highlights
Fitness Function: Evaluates the number of diagonal conflicts:
def evalNQueens(individual):
    diagonal_conflicts = 0
    for i in range(len(individual)):
        for j in range(i + 1, len(individual)):
            if abs(individual[i] - individual[j]) == abs(i - j):
                diagonal_conflicts += 1
    return diagonal_conflicts,
    
## DEAP Framework: 
Used to handle population initialization, genetic operations, and evolution.

## Customization:
Update the number of queens (NB_QUEENS) to solve larger board sizes (e.g., 12-Queens).

Adjust parameters like population size, crossover probability, mutation probability, and generations for experimentation.

## About This Project:
This code is part of my MSc Artificial Intelligence course, focusing on constraint satisfaction and evolutionary computation.

## Acknowledgments:
Framework: DEAP Documentation.

This project was created using academic materials from the CS5707 Artificial Intelligence course.

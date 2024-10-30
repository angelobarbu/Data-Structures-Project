# Algorithms and Data Structures (ADS) - ATP Cup Tennis Tournament Automation

## Author
Barbu Angelo-Gabriel  
[angelo.barbu123@gmail.com](mailto:angelo.barbu123@gmail.com)

## Project Overview

This project is a simulation of an ATP Cup Tennis Tournament, designed to automate match management between international teams of players representing their respective countries. The solution features complex data structures and algorithms that manage the flow of the tournament, player interactions, and scoring in compliance with predefined rules.

## Key Features
- **Circular Doubly Linked List**: Manages the addition and removal of participating countries.
- **Stack & Queue**: Used for player matchups and score tracking between competing countries.
- **Binary Search Tree (BST)**: Stores player data from the final four countries, sorted by personal scores.
- **Checker**: A set of automated tests verifying the solution’s correctness and efficiency.

---

## Project Structure

The project is composed of the following core files:

- **main.c**: Contains the main function handling input/output and executing solution components.
- **functions.c**: Implements the main functions and data structure operations.
- **header.h**: Defines data structures and function prototypes.
- **Makefile**: Includes build and clean targets for compilation and file management.

---

## Task Details

### Task 1: Initialize Tournament Countries
- **Description**: Create a circular doubly linked list with a sentinel node, appending countries to the list’s end.
  
### Task 2: Filter Countries
- **Description**: Eliminate countries until only a power-of-2 count remains. Countries are removed based on their initial score (the average score of players representing that country).

### Task 3: Tournament Simulation
- **Description**: Using stacks and queues, simulate matches between countries:
  - Countries remaining in the tournament are added to a stack.
  - Pairs of countries are dequeued for match play. Each player in a team competes against all players of the opposing team.
  - Scores are updated based on match results:
    - **Win**: +5 points to player score; +3 points to country score.
    - **Draw**: +2 points to player score; +1 point to country score.
  - The winner (or the first dequeued country in case of a tie) is moved to the WINNER stack.
  - Repeat until only one country remains as the tournament winner.

### Task 4: Binary Search Tree (BST) Creation
- **Description**: Players from the last four countries are organized in a BST, sorted by their final scores. Ties are broken lexicographically by player name (last name, then first name).

### Task 5: BST Search
- **Description**: Given two players, count the number of players in the BST with scores between their scores, excluding the given players.

---

## Solution Details

### functions.c - Key Functions
- **fileOpenCheck**: Verifies file access for read/write operations.
- **Memory Allocation Checks**: Functions like `doubleAllocCheck`, `listAllocCheck`, and `charAllocCheck` ensure correct memory allocation.
- **List Operations**: `deleteNode`, `pushStack`, `popStack`, `createQueue`, `enQueue`, and `deQueue` perform stack and queue manipulations.
- **BST Operations**: `newBSTnode`, `insertBST`, and `printBST` (Right-Root-Left order) manage the binary search tree.
- **Tournament Logic**: `Task3` handles country pairing, score updating, and WINNER stack management.
- **BST Scoring**: `checkBST` verifies the existence of specific players in the BST, while `countBST` counts players with scores within a specified range.

### Makefile
The Makefile provides two main targets:
- **Build**: Compiles `main.c` and `functions.c` to produce the executable.
- **Clean**: Removes object files and the executable.

---

## Running the Solution

### Prerequisites
Ensure you have the following installed:
- **C Compiler**: GCC or equivalent.
- **Make**: For automated compilation.

### Execution
1. Clone this repository.

2. Compile the project:
   ```bash
   make
   ```

3. Run the executable:
    ```bash
    ./tenis
    ```

4. To clean up generated files:
    ```bash
    make clean
    ```

---

## Checker

### Author
Eduard-Claudiu Ciurezu

### Description
The checker provides 15 test cases to validate program correctness and performance.
- data: Contains test inputs.
- ref: Contains expected outputs for comparison.
- checker.sh: Shell script that automates test execution.

### Usage
Run the checker
    ```bash
    ./checker.sh
    ```

Achieving a score of **135p / 135p** confirms correct and efficient program operation.

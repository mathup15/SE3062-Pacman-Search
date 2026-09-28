# SE3062 – Intelligent Systems
## Search Algorithms in Pac-Man

### BSc (Hons) in Computer Science
**Faculty of Computing – SLIIT**  
**Year 3 – 2026**

---

## 📌 Project Overview

This repository contains the group assignment for **SE3062 – Intelligent Systems**.

The objective of this project is to implement and evaluate classical **uninformed and informed search algorithms** using the Pac-Man environment.

The project includes implementations of:

- Depth First Search (DFS)
- Breadth First Search (BFS)
- Uniform Cost Search (UCS)
- A* Search
- Corners Problem
- Corners Heuristic
- Food Heuristic

The project demonstrates how different search strategies explore state spaces and how heuristics can improve search efficiency.

---

## 👥 Team Members

| Student ID | Name | Primary Responsibility |
|---|---|---|
| IT24103717 | Mathusha P. | Q5 – CornersProblem |
| IT24104106 | Kirushan K | Q6 – Corners Heuristic |
| IT24103583 | Anuhas HLR | Q1 – DFS & Q2 – BFS |
| IT24102092 | Begum A. W. K. | Q3 – UCS & Q4 – A* |

### Shared Responsibility

**Q7 – Food Heuristic**

Q7 is jointly handled by:

- **Mathusha P.**
- **Kirushan K**

Additional responsibilities:

- **Mathusha P.** – Initial project setup, GitHub repository setup, report preparation and integration support.
- **Kirushan K** – Heuristic testing, optimization and Q7 collaboration.
- **Anuhas HLR** – Q1/Q2 implementation, testing and documentation.
- **Begum A. W. K.** – Q3/Q4 implementation, testing and documentation.

Although tasks are divided among team members, every member is expected to understand the complete implementation and all search algorithms used in the project.

---

# 🧠 Assignment Tasks

## Q1 – Depth First Search (DFS)

**Assigned to:** Anuhas HLR

Implementation of graph-search based **Depth First Search** in `search.py`.

DFS uses a **Stack (LIFO)** as its fringe and tracks expanded states to avoid repeatedly expanding the same state.

Main function:

```python
depthFirstSearch(problem)
```

Data structure:

```python
util.Stack
```

Autograder:

```bash
py -3.11 autograder.py -q q1
```

---

## Q2 – Breadth First Search (BFS)

**Assigned to:** Anuhas HLR

Implementation of graph-search based **Breadth First Search** in `search.py`.

BFS uses a **Queue (FIFO)** and explores states level by level.

Main function:

```python
breadthFirstSearch(problem)
```

Data structure:

```python
util.Queue
```

Autograder:

```bash
py -3.11 autograder.py -q q2
```

---

## Q3 – Uniform Cost Search (UCS)

**Assigned to:** Begum A. W. K.

Implementation of **Uniform Cost Search** in `search.py`.

UCS expands the state with the lowest accumulated path cost.

The priority is based on:

```text
g(n)
```

where `g(n)` represents the actual accumulated path cost from the starting state to the current state.

Main function:

```python
uniformCostSearch(problem)
```

Data structure:

```python
util.PriorityQueue
```

Autograder:

```bash
py -3.11 autograder.py -q q3
```

---

## Q4 – A* Search

**Assigned to:** Begum A. W. K.

Implementation of the **A* Search algorithm** in `search.py`.

A* combines the accumulated path cost with a heuristic estimate.

The priority is:

```text
f(n) = g(n) + h(n)
```

where:

- `g(n)` = actual path cost from the start state
- `h(n)` = estimated remaining cost to the goal

Main function:

```python
aStarSearch(problem, heuristic)
```

Data structure:

```python
util.PriorityQueue
```

Autograder:

```bash
py -3.11 autograder.py -q q4
```

---

## Q5 – Finding All the Corners

**Assigned to:** Mathusha P.

Implementation of the **CornersProblem** in `searchAgents.py`.

The objective is to construct a state-space problem where Pac-Man must visit all four corners of the maze.

Main components include:

```python
getStartState()
isGoalState()
getSuccessors()
```

The state representation is designed to remain small and hashable while keeping track of the corners Pac-Man has visited.

Autograder:

```bash
py -3.11 autograder.py -q q5
```

---

## Q6 – Corners Problem Heuristic

**Assigned to:** Kirushan K

Implementation of an effective heuristic for the `CornersProblem`.

Main function:

```python
cornersHeuristic(state, problem)
```

The heuristic must be:

- Admissible
- Consistent
- Non-negative
- Equal to `0` at a goal state

The heuristic is designed to reduce the number of nodes expanded by A* while maintaining an optimal solution.

Autograder:

```bash
py -3.11 autograder.py -q q6
```

---

## Q7 – Eating All the Food Dots

**Assigned jointly to:** Mathusha P. & Kirushan K

Implementation of a heuristic for the provided `FoodSearchProblem`.

Main function:

```python
foodHeuristic(state, problem)
```

The heuristic must remain:

- Admissible
- Consistent

The objective is to guide A* efficiently while Pac-Man attempts to eat all remaining food dots.

Autograder:

```bash
py -3.11 autograder.py -q q7
```

---

# 🔍 Search Algorithm Summary

| Algorithm | Search Type | Fringe | Priority |
|---|---|---|---|
| DFS | Uninformed | Stack | LIFO |
| BFS | Uninformed | Queue | FIFO |
| UCS | Uninformed | Priority Queue | `g(n)` |
| A* | Informed | Priority Queue | `g(n) + h(n)` |

---

# 📂 Project Structure

```text
search/
│
├── search.py
├── searchAgents.py
├── pacman.py
├── game.py
├── util.py
├── autograder.py
├── test_cases/
└── ...
```

### Main Files

| File | Purpose |
|---|---|
| `search.py` | Q1–Q4 search algorithm implementations |
| `searchAgents.py` | Q5–Q7 search problems and heuristics |
| `util.py` | Stack, Queue and PriorityQueue implementations |
| `pacman.py` | Runs the Pac-Man environment |
| `game.py` | Core game logic and data structures |
| `autograder.py` | Automated testing |
| `test_cases/` | Autograder test cases |

> **Important:** The original file names, function names and class names should not be changed because they are used by the autograder.

---

# ⚙️ Development Environment

The project is developed and tested using:

```text
Python 3.11
```

Supported Python versions for the assignment:

```text
Python 3.9 – 3.11
```

Required packages:

```text
numpy
matplotlib
```

---

# 🚀 Setup Instructions

## 1. Clone the Repository

```bash
git clone <repository-url>
```

Move into the project directory:

```bash
cd SE3062-Pacman-Search
```

---

## 2. Verify Python

Check that Python 3.11 is installed:

```bash
py -3.11 --version
```

Expected output should be similar to:

```text
Python 3.11.x
```

---

## 3. Install Required Packages

```bash
py -3.11 -m pip install numpy matplotlib
```

---

## 4. Run Pac-Man

```bash
py -3.11 pacman.py
```

A Pac-Man game window should open.

---

# 🧪 Running the Autograder

Each question can be tested individually.

### Q1

```bash
py -3.11 autograder.py -q q1
```

### Q2

```bash
py -3.11 autograder.py -q q2
```

### Q3

```bash
py -3.11 autograder.py -q q3
```

### Q4

```bash
py -3.11 autograder.py -q q4
```

### Q5

```bash
py -3.11 autograder.py -q q5
```

### Q6

```bash
py -3.11 autograder.py -q q6
```

### Q7

```bash
py -3.11 autograder.py -q q7
```

To run the complete autograder:

```bash
py -3.11 autograder.py
```

---

# 🌿 Git & GitHub Workflow

Each member should make meaningful commits corresponding to their actual contribution.

Example commit messages:

```text
Implement DFS graph search for Q1
Implement BFS using Queue for Q2
Implement Uniform Cost Search for Q3
Implement A Star search for Q4
Implement CornersProblem state representation for Q5
Implement corners heuristic for Q6
Improve food heuristic for Q7
Add Q5 autograder evidence to report
Update project documentation
```

Avoid vague commit messages such as:

```text
update
changes
final
code
fix
```

---

# 🔀 Team Branches

Suggested development branches:

```text
main

├── anuhas-q1-q2
├── begum-q3-q4
├── mathusha-q5
├── kirushan-q6
└── mathusha-kirushan-q7
```

Members should work on their assigned branch and merge completed, tested implementations into `main`.

---

# 📊 Autograder Mark Allocation

| Question | Topic | Marks |
|---|---|---:|
| Q1 | Depth First Search | 4 |
| Q2 | Breadth First Search | 4 |
| Q3 | Uniform Cost Search | 4 |
| Q4 | A* Search | 4 |
| Q5 | CornersProblem | 8 |
| Q6 | Corners Heuristic | 8 |
| Q7 | Food Heuristic | 8 |
| **Total** | | **40** |

---

# 📈 Heuristic Performance Targets

## Q6 – Corners Heuristic

Performance is evaluated using the number of expanded nodes on `mediumCorners`.

| Nodes Expanded | Marks |
|---|---:|
| More than 2000 | 0 / 8 |
| ≤ 2000 | 4 / 8 |
| ≤ 1600 | 6 / 8 |
| ≤ 1200 | 8 / 8 |

The heuristic must remain admissible. A heuristic that produces a non-optimal solution can receive zero marks regardless of the number of expanded nodes.

## Q7 – Food Heuristic

Performance is evaluated on `trickySearch`.

| Nodes Expanded | Marks |
|---|---:|
| More than 15000 | 2 / 8 |
| ≤ 15000 | 4 / 8 |
| ≤ 12000 | 6 / 8 |
| ≤ 9000 | 8 / 8 |

---

# 📝 Report Requirements

The group report should contain a section for each question from **Q1 to Q7**.

Each question should include:

1. The specific functions or code blocks modified.
2. A clear screenshot of the autograder result.
3. A concise explanation of the implementation.
4. Explanation of the algorithms, data structures or heuristic design used.
5. Maximum **200 words per question** for the explanation.

The end of the report should contain:

- Public GitHub repository link
- Git contribution evidence
- Commit history screenshots
- Contribution graph screenshots
- Individual contribution table
- AI Usage Declaration

---

# 🤖 AI Usage Declaration

AI tools may be used for understanding concepts, generating ideas, debugging assistance, or code-related guidance where permitted by the assignment requirements.

Any use of AI tools must be declared in the final report according to the assignment instructions.

The declaration should identify:

- AI tool used
- Purpose of using the tool
- Exact prompts used, where required

---

# 📦 Final Submission

The group must submit **two separate items**.

### 1. Report

```text
<Group_ID>_Report.pdf
```

### 2. Source Code

Only the two edited files should be included in the final code ZIP:

```text
search.py
searchAgents.py
```

The ZIP should be named:

```text
<Group_ID>_Code.zip
```

Only one submission is required per group.

---

# 🎓 Viva Preparation

Every team member should understand the **entire solution**, regardless of individual task allocation.

Important topics include:

- DFS and Stack/LIFO behaviour
- BFS and Queue/FIFO behaviour
- UCS and path costs
- Priority queues
- A* Search
- `g(n)` and `h(n)`
- Admissible heuristics
- Consistent heuristics
- Graph search vs tree search
- Expanded/visited states
- State representation
- `CornersProblem`
- Corners Heuristic
- Food Heuristic
- Successor generation
- Goal testing
- Optimality of search algorithms
- Implementation choices in `search.py`
- Implementation choices in `searchAgents.py`

---

# 📌 Important Notes

- Do not rename the provided files.
- Do not rename required functions or classes.
- Use the data structures supplied in `util.py`.
- Test each question using the autograder before merging.
- Keep commits meaningful and descriptive.
- All team members should contribute through Git.
- All team members should understand the complete implementation.
- Keep screenshots of successful autograder results for the report.

---

## 👨‍💻 Contributors

**Mathusha P.** — IT24103717  
**Kirushan K** — IT24104106  
**Anuhas HLR** — IT24103583  
**Begum A. W. K.** — IT24102092  

---

### SE3062 – Intelligent Systems
**Faculty of Computing, SLIIT | 2026**

# Heuristic Algorithms for Engineering Optimization (in SageMath)

This repository contains a Jupyter Notebook (`3. Генетический алгоритм.ipynb`) that implements and compares two different heuristic optimization algorithms to solve an engineering problem.

## The Problem

The goal is to optimize the thickness profile (`h`) of a beam across 10 different points. The objective is to find a set of thickness values (between 20 and 200) that minimizes the total mechanical stress (`Sigma`) across the beam.

## Algorithms Implemented

This notebook explores two different approaches to this optimization problem:

### 1. Particle Swarm Optimization (PSO)
* **Description:** A swarm-based algorithm where each "particle" (a potential solution) moves through the solution space. Its movement is influenced by its own best-known position and the best-known position of the entire swarm (`minG` / `minT` in the code).
* **Result (Min. Stress):** ~88.89

### 2. Genetic Algorithm (GA)
* **Description:** A classic evolutionary algorithm that mimics natural selection.
    * **Selection:** The population is sorted by its fitness score.
    * **Crossover:** The "fittest" individuals are selected to "breed," exchanging genetic information (parameters).
    * **Mutation:** The worst-performing individuals are removed and replaced with new, random solutions to maintain diversity.
* **Result (Min. Stress):** ~7.30

## Conclusion

For this specific beam optimization task, the **Genetic Algorithm (GA) significantly outperformed the Particle Swarm Optimization (PSO)**, finding a solution with a much lower total stress value.

The notebook also includes a test of the GA on the classic Rosenbrock function (Cell `[b0b3cd6e]`).

---

### ⚠️ Important: How to Run

This notebook was **created using SageMath 9.5**, not standard Python.

To run this code correctly, you must have [SageMath](https://www.sagemath.org/) installed and run the Jupyter Notebook from within the Sage environment, or use a Jupyter kernel configured for SageMath. Standard Python kernels will **not** work due to syntax differences (`for i in [0..M-1]`) and specific library imports.

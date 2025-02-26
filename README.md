# Constrained K-Means

This project presents an experimental analysis of an innovative approach to **constrained clustering**, with a particular focus on **balanced Hard Clustering**. The main objective is to compare the traditional K-Means algorithm with a formulation based on **MIQP (Mixed Integer Quadratic Programming)**, exploring their performance and differences in terms of efficiency and accuracy.

## Project Description

The project compares two approaches to solving the clustering problem:

1. **Traditional K-Means**: a fast and efficient method but does not guarantee optimality and is sensitive to initial conditions.
2. **MIQP (Mixed Integer Quadratic Programming)**: a mathematical approach that allows reaching the global optimum, albeit at the expense of computational speed.

Experiments were conducted on different datasets to evaluate the impact of each method in scenarios with specific constraints.

## K-Means

The **K-Means** algorithm is one of the most widely used clustering methods due to its simplicity and computational efficiency. It operates through an iterative process involving two main steps:

1. **Assignment**: each point is assigned to the cluster with the nearest centroid.
2. **Update**: centroids are recalculated based on the assigned points.

### Advantages of K-Means:
- Simple to implement
- Efficient on large datasets

### Disadvantages of K-Means:
- Sensitive to initial conditions (random centroid selection)
- Does not guarantee global optimality
- Difficulty handling specific constraints

## MIQP (Mixed Integer Quadratic Programming)

The **MIQP** approach reformulates the constrained clustering problem as a **mixed-integer quadratic programming problem**. This technique ensures the search for the global optimal solution, unlike K-Means, which only converges to local minima.

### Characteristics of MIQP:
- **Accuracy**: guarantees the global optimum regardless of initial conditions.
- **Flexibility**: easily integrates additional constraints (e.g., cluster balancing).
- **Computational cost**: significantly higher than K-Means, especially on large datasets.

Further details on the mathematical formulation and implementation are available in the **Documentation** directory of this repository.

## Repository Structure

- **main.py**: main script for running experiments
- **/Documentation**: theoretical and technical insights on the MIQP implementation
- **/datasets**: contains the datasets used for the experiments

## Execution Instructions

To run the experiments and replicate the results:

1. **Clone the repository**:

    ```bash
    git clone <URL_REPOSITORY>
    cd <FOLDER_NAME>
    ```

2. **Select the dataset** in `main.py` by modifying the **DATASET** variable:

    - `1`: Synthetic 1
    - `2`: Synthetic 2
    - `3`: Heart Disease
    - `4`: Coverage Type

3. **Choose the test type** in `main.py` by modifying the **TEST** variable:

    - `1`: Varying the number of elements
    - `2`: Varying the number of features
    - `3`: Varying the number of clusters

4. **Run the script**:

    ```bash
    python main.py
    ```

## Requirements

Ensure the following Python packages are installed:

```bash
pip install numpy scipy matplotlib gurobipy
```

> **Note**: The MIQP algorithm requires Gurobi Optimizer. Ensure you have a valid license and the package is correctly configured.

## Authors

This project was developed by **Lorenzo Baiardi** and **Thomas Del Moro** as part of the **Optimization Techniques for Machine Learning** course (academic year 2023).

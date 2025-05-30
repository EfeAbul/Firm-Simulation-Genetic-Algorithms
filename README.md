
# Firm Behavior Simulation using Genetic Algorithms

This project simulates firm behavior in a competitive market using **genetic algorithms**. It models how firms iteratively adjust their production quantities to maximize profit, based on demand conditions and interactions with other firms. This is developed as part of an academic course project.

---

## Project Overview

- **Goal**: Simulate and analyze how firms learn optimal production levels through genetic evolution.
- **Approach**:
  - Represent each firm as a binary chromosome that encodes production quantity.
  - Use a fitness function based on profit = revenue - cost.
  - Apply genetic operations (selection, crossover, mutation) over multiple iterations.

---

##  Key Features

- **Number of firms**: 30
- **Chromosome length**: 10-bit binary string
- **Demand model**: Linear inverse demand with interaction term (`b`)
- **Labeling Parameters**:
  - `Y`: 2nd last digit of student number (used in parameter tuning)
  - `Z`: Last digit of student number
  - `b = (-1)^Z * (0.50 + 0.01 * Y)` – captures whether firms are substitutes or complements
- **Genetic Parameters**:
  - Crossover probability: `pcross = 0.300 + 0.01*Y + 0.001*Z`
  - Mutation probability: `pmut = 0.003 + 0.0001*Y + 0.00001*Z`

---

## Genetic Algorithm Workflow

1. **Initialize population** with binary strings (firms).
2. **Decode** each chromosome into a production quantity.
3. **Calculate fitness** using the profit function.
4. **Select parents** using fitness-weighted probabilities.
5. **Apply crossover and mutation** to create the next generation.
6. Repeat for 1000 generations.

---

## Visualizations

- Mean production quantity over time
- Mean profit per firm over time
- Distribution of fitness and quantities in the population

---

##  Insights

- The algorithm reflects how decentralized firms can adapt production strategies over time.
- Different `b` values (competition vs complementarity) lead to different equilibrium outcomes.
- Mutation and crossover rates control exploration and convergence behavior.

---

##  File

- `Genetic_Algorithm.ipynb`: Jupyter notebook containing the full implementation, parameter definitions, simulation, and plots.

---

##  How to Run

1. Install required libraries:
   ```bash
   pip install numpy matplotlib
   ```

2. Open the notebook:
   ```bash
   jupyter notebook Genetic_Algorithm.ipynb
   ```

3. Replace Y and Z with custom numeric values to adjust simulation parameters.
4. Run all cells to simulate the firm learning behavior.

---

##  Requirements

- Python 3.x
- NumPy
- Matplotlib

---

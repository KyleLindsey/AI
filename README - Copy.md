# 🧭 Traveling Salesman Problem with A* and Heuristic Comparison

This Jupyter Notebook demonstrates how to solve the **Traveling Salesman Problem (TSP)** using **A\* Search**, comparing two heuristics:

- **Minimum Spanning Tree (MST) Heuristic** — tight, graph-aware
- **Manhattan Distance Heuristic** — loose, coordinate-based

Cities are randomly generated in a 2D plane, and the notebook includes detailed performance comparisons and visualizations.

---

## 📂 Project Structure

---

## 🚀 Features

- ✅ A\* Search algorithm tailored for TSP
- ✅ Two heuristics implemented and compared:
  - MST-based heuristic (tight lower bound using graph structure)
  - Manhattan-style heuristic (based on grid-style coordinate distance)
- ✅ Random city generation with optional seed
- ✅ Interactive plots of the TSP tour using `matplotlib`
- ✅ Execution time and total path cost tracking
- ✅ Embedded explanation of heuristic quality

---

## 🗺️ Random City Generation

Each time the notebook runs, it generates `NUM_CITIES` random 2D coordinates for cities.  
You can set a `SEED` to reproduce the same city layout:

```python
NUM_CITIES = 10
SEED = 42  # Use None for random each run
## 🧠 Why Compare MST vs Manhattan?

In this notebook, we use randomly generated city coordinates to solve the Traveling Salesman Problem (TSP) using A* search with two different heuristics. Here's why the comparison is meaningful:


### 🔍 Heuristics Compared

#### ✅ Minimum Spanning Tree (MST) Heuristic
- Computes a **Minimum Spanning Tree** over all **unvisited cities**.
- Adds:
  - Cost from the **current city** to the closest unvisited city.
  - Cost to return from any unvisited city back to the **start city**.
- Reflects a **realistic lower bound** for the remaining cost.
- Well-suited for Euclidean TSP instances with random coordinates.

#### ❌ Manhattan Distance Heuristic
- Sums the **Manhattan distances** (`|x₁ - x₂| + |y₁ - y₂|`) from the current city to all unvisited cities.
- Ignores graph structure, edge weights, or tour constraints.
- Simple, but overly **optimistic** and **uninformed** in non-grid environments.

---

### 📊 Performance Summary

| Feature                 | MST Heuristic              | Manhattan Heuristic         |
|-------------------------|----------------------------|-----------------------------|
| Structure Awareness     | ✔ Uses actual graph edges  | ❌ Ignores graph structure   |
| Tour-Awareness          | ✔ Reflects path structure  | ❌ No path consideration     |
| Admissibility           | ✔                          | ✔                            |
| Tightness of Estimate   | High (informed bound)      | Low (naive bound)            |
| Search Efficiency       | Fewer nodes explored       | More redundant paths         |
| Best for Random Layouts | ✔                          | ❌                            |

---

### 🎓 Conclusion

> The **MST heuristic consistently outperforms** Manhattan in TSP with random coordinates due to its deeper structural insight into the problem.  
> While both heuristics are admissible (i.e., they never overestimate), **MST is much tighter**, leading to faster solutions and fewer explored states.

---

## 📘 References

- A* Search: [Wikipedia](https://en.wikipedia.org/wiki/A*_search_algorithm)
- MST Heuristic: Used in branch-and-bound and approximation methods
- Manhattan Distance: Classic heuristic used in grid-based problems

---

## 📜 License

MIT License – Free to use, adapt, and share.

# Delivery Route Optimization
### ADA Capstone Project – E-Commerce Logistics

A complete implementation of multi-paradigm delivery route optimization for an e-commerce platform, covering recurrence, greedy, dynamic programming, graph algorithms, and TSP.

---

## Project Structure

```
delivery-route-mini-project/
├── notebooks/
│   └── delivery_route_optimization.ipynb   # Full code & analysis
├── images/
│   ├── algo_performance.png                # Execution time + profit/weight chart
│   ├── route_map.png                       # MST & TSP route visualization
│   └── tsp_scalability.png                 # TSP BF vs Held-Karp growth
├── requirements.txt
└── README.md
```

---

## Algorithm Strategies

| Task | Algorithm | Paradigm | Complexity |
|------|-----------|----------|------------|
| Route cost estimation | Recursive DFS | Recurrence | O(n!) |
| Parcel selection | Value/weight ratio sort | Greedy | O(n log n) |
| Delivery feasibility | Sequential time tracking | DP | O(n) |
| Shortest path | Dijkstra SSSP | Graph | O((V+E) log V) |
| Minimum spanning tree | Prim's algorithm | Graph | O(E log V) |
| Optimal tour (small n) | Brute-force enumeration | Exhaustive | O(n!) |
| Optimal tour (medium n) | Held-Karp bitmask DP | DP | O(n²·2ⁿ) |

---

## Setup & Run

```bash
# 1. Clone the repo
git clone https://github.com/<yourname>/delivery-route-mini-project-<yourname>.git
cd delivery-route-mini-project-<yourname>

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Launch JupyterLab
jupyter lab notebooks/delivery_route_optimization.ipynb
```

---

## Key Outputs

- **Greedy selection** picks parcels with the best value-to-weight ratio within vehicle capacity.
- **DP time-window validation** checks each delivery against its allowed arrival window.
- **Dijkstra** finds shortest path from warehouse to each customer.
- **Prim's MST** builds a minimum cost spanning network (no return trip required).
- **Held-Karp TSP** returns the globally optimal delivery sequence.
- **Profiling plots** show algorithm runtime growth and parcel value distribution.

---

## Reflection

- **TSP becomes infeasible** beyond ~12 stops for brute-force; Held-Karp extends practical limit to ~20.
- **Greedy is fastest** but may miss time-window constraints; DP adds that safety check.
- **Optimal route ≠ realistic route**: waiting at early delivery windows adds real-world cost.
- **Future improvement**: add fuel cost per km and multi-vehicle VRP support.

---



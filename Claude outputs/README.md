# ORIE 5380 Course Project: Store Pickup Location Selection

Optimization models (built with Gurobi) for choosing which stores in a retail chain should offer in-store pickup and returns in a pilot program in Manhattan.

Course: ORIE 5380 – Optimization Methods, Cornell Tech (Fall 2026)

## Overview

An online retailer wants to pilot in-store pickup and returns at `p` of a chain's `N` stores. Given customer delivery addresses and candidate store locations, the models select which stores to include.

**Part 1: Minimizing travel time**
- Model 1: select `p` stores to minimize the *average* customer travel time
- Model 2: select `p` stores to minimize the *worst-case* customer travel time

**Part 2: Selecting stores based on predicted usage**
- Model 3: minimize expected travel time, using one usage prediction per customer
- Model 4: maximize the expected number of customers using the service, using one prediction per customer–store pair

Each model is solved for `p = 1, ..., 10` with a 60-second time limit per run. The results compare runtime, optimality gap, travel-time metrics, and maps of customer–store assignments.

## Setup

1. Install dependencies:
   ```bash
   pip install gurobipy numpy pandas matplotlib jupyter
   ```
2. Get a free Gurobi academic license. These models are too large for the restricted license bundled with `pip install gurobipy`.
   - Run `grbgetkey <your-key>` while on the Cornell network or VPN
   - Put `gurobi.lic` in your home folder, or set the `GRB_LICENSE_FILE` environment variable to its path
   - Restart the Jupyter kernel. Running `gp.Env()` should print "Academic license"
3. Open the notebook and run the license-check cell first.

> `gurobi.lic` contains a personal license key. Never commit it to this repo.

## Repository Structure

```
.
├── project.ipynb      # Main notebook: data loading, models, plots
├── data/              # Customer and store locations, travel times, predictions
├── figures/           # Plots exported for the reports
└── README.md
```

## Deliverables

| Item | Due |
|------|-----|
| Part 1 report | 11/18 |
| Part 1 quiz | 11/19 (in class) |
| Part 2 report | 11/30 |
| Part 2 quiz | 12/01 (in class) |

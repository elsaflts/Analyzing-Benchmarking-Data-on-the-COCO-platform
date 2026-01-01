# COCO BBOB Benchmark Analysis

This repository contains Jupyter notebooks used to analyze the COCO (Comparing Continuous Optimizers) benchmark data in order to identify top-performing derivative-free optimization algorithms using **Expected Running Time (ERT)**.

The analysis covers **three test suites**:
- **BBOB Noiseless**
- **BBOB Noisy**
- **BBOB Bi-Objective**

For each test suite, two complementary methods are implemented:
1. **Strict Winner Method** – selects the absolute best algorithm (minimum ERT)
2. **Factor Method** – selects near-optimal algorithms within a chosen performance factor


## Repository Structure

├── ppdata/ # COCO benchmark raw data (required, not versioned)
├── results/ # Generated CSV outputs
│
├── Best Alg YYYY.ipynb
├── BBOB noisy YYYY.ipynb
├── BBOB biobj YYYY.ipynb
│
├── comparing years for the BBOB test Suite.ipynb
├── comparing years for the BBOB - noisy test Suite.ipynb
├── comparing years for the BBOB - biobj test Suite.ipynb
│
├── Factor method with the bbob test suite.ipynb
├── Factor method with the bbob noisy test suite.ipynb
├── Factor method with the bbob biobj test suite.ipynb
│
├── Final Results.ipynb
└── Getting familiar with the data.ipynb


---

## Execution Order (IMPORTANT)

Notebooks **must be run in the correct order**, as several steps depend on CSV files generated earlier.

---

## 1. BBOB Noiseless Test Suite

### 1.1 Strict Winner Method (per year)

Run each year independently (data loading is time-consuming):

Best Alg 2009.ipynb
Best Alg 2010.ipynb
Best Alg 2012.ipynb
Best Alg 2013.ipynb
Best Alg 2015.ipynb
Best Alg 2016.ipynb
Best Alg 2017.ipynb
Best Alg 2018.ipynb
Best Alg 2019.ipynb
Best Alg 2020.ipynb
Best Alg 2021.ipynb
Best Alg 2022.ipynb
Best Alg 2023.ipynb
Best Alg 2024.ipynb

Each notebook outputs: results/best_algos_YYYY.csv

---

### 1.2 Aggregate Results Across Years

After all yearly notebooks are executed: comparing years for the BBOB test Suite.ipynb
Output: results/global_best_algos.csv


This file is required for the factor method.

---

### 1.3 Factor Method (Near-Optimal Algorithms)

Factor method with the bbob test suite.ipynb

This notebook:
- Uses `global_best_algos.csv`
- Prompts the user to choose a performance factor α
- Extracts all algorithms within α × best ERT

---

## 2. BBOB Noisy Test Suite

### 2.1 Strict Winner Method (per year)

BBOB noisy 2009.ipynb
BBOB noisy 2010.ipynb
BBOB noisy 2012.ipynb
BBOB noisy 2016.ipynb

Each notebook outputs:
results/best_algos_noisy_YYYY.csv

---

### 2.2 Aggregate Results Across Years

comparing years for the BBOB - noisy test Suite.ipynb


---

### 2.3 Factor Method



Factor method with the bbob noisy test suite.ipynb


---

## 3. BBOB Bi-Objective Test Suite

### 3.1 Strict Winner Method (per year)



BBOB biobj 2016.ipynb
BBOB biobj 2019.ipynb
BBOB biobj 2021.ipynb
BBOB biobj 2022.ipynb
BBOB biobj 2023.ipynb


Each notebook outputs:


results/best_algos_biobj_YYYY.csv


---

### 3.2 Aggregate Results Across Years



comparing years for the BBOB - biobj test Suite.ipynb


---

### 3.3 Factor Method



Factor method with the bbob biobj test suite.ipynb


---

## Final Analysis



Final Results.ipynb


This notebook consolidates results from all three test suites and produces the final tables and visualizations.

---

## Notes

- All analyses rely on **Expected Running Time (ERT)** from the COCO platform.
- Algorithms with infinite ERT are automatically discarded.
- Notebooks are intentionally split by year to limit runtime and memory usage.
- The `ppdata/` directory must contain the COCO benchmark data and is not included in this repository.




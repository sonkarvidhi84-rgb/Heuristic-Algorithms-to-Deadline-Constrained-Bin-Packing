# Heuristic Algorithms to Deadline-Constrained Bin Packing

**Anant Rajput (27252), Revathy Ramesh (26442), Vidhi Sonkar (25999)**  
April 2026

---

## 1. Introduction

During a discussion with friends, we were talking about how cloud systems like Kubernetes manage to place so many workloads onto servers efficiently without wasting resources or causing overload. While thinking through a simple example, we imagined each task requiring some amount of CPU or memory and each server having a fixed capacity, with the goal of fitting all tasks using as few servers as possible.

As we tried to do this, we struggled to arrange them efficiently, and that’s when we came across the **bin packing problem**, which models exactly this situation—placing items of different sizes into a minimum number of bins without exceeding their capacity.

---

## 2. Objective

This project aims to design, implement, and evaluate algorithms for a variant of the **Bin Packing problem** where each item has an explicit expiry deadline.

- **Primary Objective:**  
  Minimize the number of bins used while maximizing the number of items successfully packed before expiry.

- **Secondary Objective:**  
  Minimize the waste rate.

---

## 3. Challenges

Bin packing is **NP-hard**, so finding the optimal placement is computationally expensive.

In real-world systems like Kubernetes:
- Decisions must be made quickly  
- Multiple resource constraints exist  
- Workloads are dynamic  

Hence, only approximate (**heuristic**) solutions are practical.

---

## 4. Traditional Algorithms

- **First Fit Decreasing (FFD):**  
  An offline heuristic proven to use at most  
  `(11/9) * OPT + 6/9` bins.

- **Next Fit (NF):**  
  An online algorithm with a worst-case bound of  
  `2 * OPT` bins.

---

## 5. Proposed Work

Focusing primarily on the **1D Bin Packing problem**, we will implement and compare three algorithms:

1. **First Fit Decreasing (FFD):**  
   Used as an offline baseline.

2. **Next Fit (NF):**  
   Used as an online baseline.

3. **Deadline-Aware Best Fit (DABF):**  
   Uses deadline co-location and urgency scoring.

---

## Evaluation Plan

We will benchmark these algorithms across five distributions:

- Uniform  
- Bimodal  
- Skewed  
- Tight  
- Loose  

Experiments will be conducted with varying numbers of items and compared against a **brute-force optimal solver** for small instances.

If time permits, we will extend the framework to **2D Bin Packing**.

---
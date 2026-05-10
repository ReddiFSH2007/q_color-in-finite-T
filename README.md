# Finite-Temperature Potts Model Recurrence Order Solver

This repository contains a highly optimized C++ implementation for calculating the degree of the minimal polynomial (order of linear recurrence) for the transfer matrix of the Potts model at $T > 0$ on grid graphs.

## How to Run

### 1. Compile
g++ -O3 -march=native -fopenmp main.cpp -o main

### 2. Execute
.\main.exe

## Algorithmic Highlights
* Thermal State Expansion (T > 0)
* Finite Field Arithmetic (Modulo 2147483647)
* CSR Graph Flattening for Cache Locality
* Berlekamp-Massey for O(N^2) Recurrence Extraction

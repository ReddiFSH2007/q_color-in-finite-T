# Finite-Temperature Potts Model Recurrence Order Solver

This repository contains a highly optimized C++ implementation for calculating the degree of the minimal polynomial (order of linear recurrence) for the transfer matrix of the Potts model at $T > 0$ on grid graphs.

## How to Run

### 1. Compile
g++ -O3 -march=native -fopenmp main.cpp -o main

### 2. Execute
.\main.exe

### 3. Expected Output
w = 0.1 (mod 1503238553)

q = 2 : 1 2 3 6 10 20 35 70 126 252 462 

q = 3 : 1 2 4 10 25 70 196 574 1681 5002 14884 

q = 4 : 1 2 4 10 26 76 232 750 2494 8524 29624 

q = 5 : 1 2 4 10 26 76 232 750 2494 8524 29624 

q = 6 : 1 2 4 10 26 76 232 750 2494 8524 29624 

## Algorithmic Highlights
* Thermal State Expansion (T > 0)
* Finite Field Arithmetic (Modulo 2147483647)
* CSR Graph Flattening for Cache Locality
* Berlekamp-Massey for O(N^2) Recurrence Extraction

Note on the Sequence Length: The loop parameter is explicitly set to 2 * d[m] + 50. The Berlekamp-Massey algorithm requires at least 2d terms to resolve a linear recurrence of order d. The additional 50 acts as a safety buffer. If the computed recurrence order matches the theoretical upper limit exactly, the calculation is correct. However, if the solver returns the upper limit plus 25 (consuming half the buffer), it indicates that the algorithm failed to find a closed recurrence within the given sequence, meaning the result is incorrect.


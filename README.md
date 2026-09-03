<kbd>ECE2112<kbd>
# ECE 2112 - Programming Assignment #02

**Celine Fatima C. Mendoza | 2ECE-C**
# EXPERIMENT 2: NUMERICAL PYTHON (NUMPY)

This repository contains programming assignment 2 for the **ADVANCED COMPUTER PROGRAMMING AND ALGORITHMS** ```[ECE2112]``` course. It consists of three programming problems covering **Module 2 - Numpy**.


   ## I. Intended Learning Outcomes
   At the end of this laboratory activity, the student should be able to:

   1. create and reshape NumPy arrays using appropriate NumPy functions;
   2. perform vectorized numerical operations on an ndarray;
   3. compute array statistics and use Boolean conditions to select elements; and
   4. save computed NumPy arrays as **.npy** files.

  ## II. Programming Problems

### A. REPRODUCIBLE NORMALIZATION PROBLEM
Create a reproducible random 5 × 5 integer ndarray named **X**. Use the following two statements before
performing any calculation: 

  `np.random.seed(2112)`  
  `X = np.random.randint(10, 101, size=(5, 5))`  

Normalize the complete array using
  $`\ Z = X - X̄ / σ `$

### Function: 
  ~ **np.random.seed()** ```np.random.seed(2112)``` - 
  ~ **np.random.randint()** ```np.random.randint(10, 101, size=(5, 5))``` - 

  ```python
import numpy as np

np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

X_mean = np.mean(X)
X_std = np.std (X)

X_normalized = (X-X_mean)/X_std

print ("X = ", X)
print ("X_normalized = ", X_normalized)
print ("Mean = ", np.mean(X_normalized))
print ("Standard Deviation = ", np.std(X_normalized))

np.save("X_normalized.npy", X_normalized)
```


###

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
                                $`\ Z = X - x̄ / σ `$  
where ¯x is the mean of all 25 elements and σ is their population standard deviation as returned by
NumPy’s default **std()** call. Store the normalized array in `X_normalized`.

### Function: 
  ~ **np.random.seed()** -
  
   *Example:* 
     ```np.random.seed(2112)```   
     
  ~ **np.random.randint()** -  
  
   *Example:*    
        ```np.random.randint(10, 101, size=(5, 5))```  

   ~ **np.mean()** -  

   *Example:* 
       ```np.mean(X)```  

   ~ **np.std()** -  

   *Example:*
      ```np.std (X)```  

   ~ **np.save()** -  

   *Example:*  
      ```np.save("X_normalized.npy", X_normalized)``` 

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


### B. CUBES DIVISIBLE BY 4 PROBLEM
Using NumPy, create the first 100 positive integers, cube every element, and reshape the result into a
10 × 10 ndarray named C. Thus, C begins with 1<sup>3</sup> and ends with 100<sup>3</sup>.   
Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in
div_by_4. Preserve NumPy’s normal row-major selection order.

### Function:
   ~ **np.arange ()** -  
   
   *Example:* 
      ```np.arange (1, 101, 1)```  
      
   ~ **.reshape()** -  
   
   *Example:* 
   ```C.reshape(10,10)```

   
   ```python
C = np.arange (1, 101, 1)
C = C ** 3
C = C.reshape(10,10)

div_by_4 = C[C%4 == 0]

print ("Shape of C = ", C.shape)
print ("Array divisible by 4 = ", div_by_4)
print ("The number of selected elements =", div_by_4.size )

np.save("div_by_4.npy", div_by_4)
```




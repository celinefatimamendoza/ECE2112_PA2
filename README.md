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
  ~ **np.random.seed()** - This function initializes random-generated values that present the same sequence every time.  
  
   *Example:*  
     ```np.random.seed(2112)```   
     
  ~ **np.random.randint()** - This function generates random integers from a specific range given by the coder.   
  
   *Example:*    
        ```np.random.randint(10, 101, size=(5, 5))``` - In this example, the *(5,5)* shows the size of the array the matrix will be. The first parameter that has *10* specifies the lowest possible integer. The parameter beside it is the upper boundary, which is exclusive, so it ends at 100.  

   ~ **np.mean()** - This computes the average value of the elements from the specified data.  

   *Example:*  
       ```np.mean(X)```  

   ~ **np.std()** - This computes the standard deviation of the elements from the specified data.  

   *Example:*  
      ```np.std (X)```  

   ~ **np.save()** - This saves the file as an `.npy` file.  

   *Example:*    
      ```np.save("X_normalized.npy", X_normalized)``` - The ` "X_normalized.npy" ` is the file name where the data will be stored. Whereas `X_normalized` is the data inside the program.  

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
**10 × 10 ndarray** named **C**. Thus, *C* begins with 1<sup>3</sup> and ends with 100<sup>3</sup>.   

Use a Boolean condition on **C** to obtain every cubed value divisible by 4. Store the selected values in
`div_by_4`. Preserve NumPy’s normal row-major selection order.  

### Function:  
   ~ **np.arange ()** - This creates an array with evenly spaced integers over a given interval.  
   
   *Example:*     
      ```np.arange (1, 101, 1)``` - In this example, the first parameter inside the parentheses shows what value the array will start at, which is `1`. The middle parameter indicates what value it will stop. This is also exclusive, making it end at 100. The last parameter explains the gap between each value.  
      
   ~ **.reshape()** - This changes the dimensions of an array without modifying the values inside it.  
   
   *Example:*   
   ```C.reshape(10,10)``` - In this example, it states that the array will be reshaped into 10 rows and 10 columns.  

   ~ **div_by_4** -  This is a Boolean condition that works as a determining function for which cubed integers are divisible by 4.  

   ~ **np.save()** - This saves the file as an `.npy` file.  

   *Example:*    
      ```np.save("div_by_4.npy", div_by_4)``` - The ` "div_by_4.npy" ` is the file name where the data will be stored. Whereas `div_by_4` is the data inside the program.   

   
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


### C. ABOVE-MEAN SQUARES PROBLEM  
Create a **6 × 6 ndarray** named **S** containing the squares of the first **36** positive integers in increasing
row-major order. Compute the mean of all elements of **S** and store it in `S_mean`. Then use Boolean
filtering to select only the elements strictly greater than `S_mean`. Store these values in `above_mean`.  

### Function:  
   ~ **np.arange ()** - This creates an array with evenly spaced integers over a given interval.  

   *Example:*   
   ```np.arange (1, 37, 1)``` - In this example, the first parameter inside the parentheses shows what value the array will start at, which is `1`. The middle parameter indicates what value it will stop. This is also exclusive, making it end at 36. The last parameter explains the gap between each value.  
   
   ~ **.reshape()** - This changes the dimensions of an array without modifying the values inside it.  

   *Example:*  
   ```S.reshape(6,6)``` - In this example, it states that the array will be reshaped into 6 rows and 6 columns. 

   ~ **above_mean** - This is a Boolean condition that works as a determining function for which elements are greater than the `S_mean`.  

   ~ **np.save()** - This saves the file as an `.npy` file.  

   *Example:*    
      ```np.save("above_mean.npy", above_mean)``` - The ` "above_mean.npy" ` is the file name where the data will be stored. Whereas `above_mean` is the data inside the program. 

   ```python
S = np.arange (1, 37, 1)
S = S ** 2
S = S.reshape(6,6)

S_mean = np.mean(S)

above_mean = S[S > S_mean]

print ("S =", S)
print ("S_mean = ", S_mean)
print ("above_mean = ", above_mean)
print ("The number of selected elements =", above_mean.size )

np.save("above_mean.npy", above_mean)
```


#### *Thank you for reading!*  
  
  
**README file Version History**   
*September 3, 2026* - Published the repository (included files: 3 .npy, 1 .ipynb, and README.md).  
*September 5, 2026* - Completed the content of the README file.


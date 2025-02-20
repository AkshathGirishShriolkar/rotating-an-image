# Rotating The Matix

rotate the 2d matrix given by 90 degrees anticlockwise inplace. note that no new 2d matrix should be created.

**eg:**          [[1, 2, 3],[4 ,5 ,6],[7 ,8 ,9]]

**answer:** [[3, 6, 9], [2, 5, 8], [1, 4, 7]]

## Input Format

s= a string

 k= an integer

# Output Format

- n where n is an integer

# Constraints

- 0 <= s.length < 10^6
- 0 <= n < 10^6

## Testcases

- Input:
   
   ```
   [[5, 12, 9],[3, 7, 14],[8, 2, 10]]
   ```
   
- Output:
   
   ```
   [[9, 14, 10], [12, 7, 2], [5, 3, 8]]
   ```
---
  
- Input:
   
   ```
   [[1, 2, 3, 4, 5, 6],[7, 8, 9, 10, 11, 12],[13, 14, 15, 16, 17, 18],[19, 20, 21, 22, 23, 24],[25, 26, 27, 28, 29, 30],[31, 32, 33, 34, 35, 36]]
   ```
   
- Output:

   ``` 
   [[6, 12, 18, 24, 30, 36], [5, 11, 17, 23, 29, 35], [4, 10, 16, 22, 28, 34], [3, 9, 15, 21, 27, 33], [2, 8, 14, 20, 26, 32], [1, 7, 13, 19, 25, 31]]
   ```
---

- Input:
   
    ```
   [[11, 22, 33, 44, 55],[66, 77, 88, 99, 10],[20, 30, 40, 50, 60],[70, 80, 90, 15, 25],[35, 45, 55, 65, 75]]
    ```
   
- Output:

   ``` 
   [[55, 10, 60, 25, 75], [44, 99, 50, 15, 65], [33, 88, 40, 90, 55], [22, 77, 30, 80, 45], [11, 66, 20, 70, 35]]
   ``` 
---

- Input:

   ```
   [[-5, 12, -9],[3, -7, 14],[-8, 2, -10]]
    ```
   
- Output:

   ```
   [[-9, 14, -10], [12, -7, 2], [-5, 3, -8]]
   ```
---

- Input:

   ```
   [[1, 0, 1, 0],[0, 1, 0, 1],[1, 0, 1, 0],[0, 1, 0, 1]]
   ```
   
- Output:

   ```
   [[0, 1, 0, 1], [1, 0, 1, 0], [0, 1, 0, 1], [1, 0, 1, 0]]
   ```
---
   


## Solution

- we create a variable "leng" to store the length of a matrix. a given matrix is a square matrix, the length of the outer array and the length of the inner array are equal
- we then, reverse the order of the rows in the outer matrix 
- then we iterate through the original array
- then we iterate through the smaller array. basically 2 nested loops
- we then swap the elements which are at image position with respect to the diagonal(topleft to bottom right in this case)
- note that the above operation must be applied to only half of the elements, since doing this to all the elements will just give the original array
- so basically, the inner loop must iterate through i to leng where i is the ith array in the larger array

```
leng=len(image)
for i from 0 to leng-1:
    image[i].reverse()
for i from 0 to leng-1:
    for j from i to leng-1:
        swap image[i][j] and image[j][i]
 ```

### Implementation

```
leng=len(image)
for i in range(len(image)):
    image[i].reverse()
for i in range(len(image)):
    for j in range(i, len(image)):
        (image[i])[j], image[j][i]=image[j][i],(image[i])[j]
```

# Javascript Algorithm and Data Structures
List of solved Javascript Algorithm and Data Structures

### Table of Contents

| No. | Questions |
| --- | --------- |
|   | **Algorithms** |
|1  | [Bubble Sorting in JavaScript](#bubble-sort) |

## Algorithms
    
1. ### Bubble Sorting in JavaScript

Bubble sort algorithm is an algorithm that sorts the array by comparing two adjacent elements and swaps them if they are not in the intended order. Here order can be anything like increasing order or decreasing order.

How Bubble-sort works
We have an unsorted array `array = [1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]` the task is to sort the array using bubble sort. 

Bubble sort compares the element from index 0 and if the 0th index is less than 1st index then the values get swapped and if the 0th index is less than the 1st index then nothing happens.

then, the 1st index compares to the 2nd index then the 2nd index compares to the 3rd, and so on…

    ```javascript
    
     function bubbleSort(array) {
        for(let i = 0; i < array.length; i++){
            for(let j = 0; j < (array.length - i - 1); j++){
              if(array[j] >= array[j + 1]){
                const temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
              }
            }
        }
        return array;
     }

     const sortedArray = bubbleSort([1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92])
     
    ```


   **[⬆ Back to Top](#table-of-contents)**

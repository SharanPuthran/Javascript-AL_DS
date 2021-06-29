# Javascript Algorithm
List of personally solved Javascript Algorithm

### Table of Contents

| No. | Questions |
| --- | --------- |
|   | **Algorithms** |
|1  | [Bubble Sorting in JavaScript](#bubble-sort) |
|2  | [Selection Sorting in JavaScript](#selection-sort) |
|3  | [Inventory Update](#inventor-update) |

## Algorithms
    
1. ### Bubble Sorting in JavaScript

    Bubble sort algorithm is an algorithm that sorts the array by comparing two adjacent elements and swaps them if they are not in the intended order. Here order can be anything like increasing order or decreasing order.

    How Bubble-sort works
    We have an unsorted array `array = [1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]` the task is to sort the array using bubble sort. 

    Bubble sort compares the element from index 0 and if the 0th index is less than 1st index then the values get swapped and if the 0th index is less than the 1st index then nothing happens.

    then, the 1st index compares to the 2nd index then the 2nd index compares to the 3rd, and so on…
    
    Time Complexity in worst case: `O(n²)` 
    
    Number of Swaps in worst case: `n - 1`
    
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
    const sortedArray = bubbleSort([1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]);
    console.log(sortedArray) // Output : [ 1, 1, 2, 2, 4, 8, 32, 43, 43, 55, 63, 92, 123, 123, 234, 345, 5643 ]
```

   **[⬆ Back to Top](#table-of-contents)**

2. ### Selection Sorting in JavaScript

    This algorithm divides the input array into two sublists - a sorted and unsorted sublist. The sorted list is located at the start of the collection, and all elements to the right of the final sorted element are considered unsorted.

    Initially, the sorted list is empty, while the rest of the collection is unsorted. Selection Sort goes through the unsorted sublist and finds the smallest or largest element.

    The element is then swapped with the leftmost element of the unsorted sublist. Then, the sorted sublist is expanded to include that element.

    This is repeated, finding the fitting element, swapping it with the leftmost element of the unsorted list, and expanding the sorted list to encompass it.

    After each iteration, one less element needs to be checked, until the entire array or list is sorted. In other words, after the k-th iteration, the first k elements of the array or list are guaranteed to be sorted.
    
    Time Complexity in worst case: `O(n²)`
    
```javascript
    function selectionSort(array) {
      const arrLen = array.length;
      for(let i = 0; i < arrLen; i++){
        let minVal = i;
        for(let j = i + 1; j < arrLen; j++){
          if(array[j] < array[minVal]){
            minVal = j
          }
        }
        if(minVal != i){
          let temp = array[i];
          array[i] = array[minVal];
          array[minVal] = temp;
        }
      }
      return array;
    }

    const returnArray = selectionSort([1, 4, 2, 8, 345, 123, 43, 32, 5643, 63, 123, 43, 2, 55, 1, 234, 92]);
    console.log(returnArray) // Output : [ 1, 1, 2, 2, 4, 8, 32, 43, 43, 55, 63, 92, 123, 123, 234, 345, 5643 ]
```

   **[⬆ Back to Top](#table-of-contents)**
   
   
3. ### Inventory Update

    *Problem Statement* : Compare and update the inventory stored in a 2D array against a second 2D array of a fresh delivery. Update the current existing inventory item quantities (in arr1). If an item cannot be found, add the new item and quantity into the inventory array. The returned inventory array should be in alphabetical order by item.
    
    *Approach* : Reverse the inner arrays and convert to map, then update the inventories and convert back to a 2D array in the original format.
    
```javascript
   function updateInventory(arr1, arr2) {
     let currrentInvMap = new Map(arr1.map( (el) => el.reverse() ));
     let newInvMap = new Map(arr2.map( (el) => el.reverse() ));
     for( let [product, value] of newInvMap ){
       if(currrentInvMap.has(product)){
         currrentInvMap.set(product, currrentInvMap.get(product) + value );
       }
       else{
         currrentInvMap.set(product, value)
       }
    }
    return [...currrentInvMap].sort().map( (el) => el.reverse() );
  }

    // Example inventory lists
    var curInv = [
        [21, "Bowling Ball"],
        [2, "Dirty Sock"],
        [1, "Hair Pin"],
        [5, "Microphone"]
    ];

    var newInv = [
        [2, "Hair Pin"],
        [3, "Half-Eaten Apple"],
        [67, "Bowling Ball"],
        [7, "Toothpaste"]
    ];

    const returnValue = updateInventory(curInv, newInv);
    console.log(returnValue);
```

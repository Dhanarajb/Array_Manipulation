# Array_Manipulation
#### Reverse an array.
```
   const arr = [1,2,3,4,5]

   function reverseArr(arr){
     let i=0;
     let j=arr.length-1
     while(i<j){
       const temp = arr[i];
       arr[i]=arr[j]
       arr[j]=temp
       i++;
       j--;
     }
   }
   reverseArr(arr)
   console.log(arr)
```
#### Find the maximum and minimum elements in an array.
```
function maxNumMinNum(arr){
     let max = arr[0]
     let min = arr[0]
     for(let chr of arr){
       if(chr > max){
         max = chr
       }
       if(chr < min){
         min = chr
       }
     }
     
     return {min,max}
   }
   console.log(maxNumMinNum(arr))
```
#### Sum all the elements in an array.
```
function sumOfArr(arr){
     let sum =0
     for(let chr of arr){
       sum += chr
     }
     return sum
   }
   console.log(sumOfArr(arr))
```
#### Find the average of elements in an array.
```
function avag(arr){
  let sum = arr.reduce((acc,val)=>acc+val,0)
  let avg = sum/arr.length
  return avg
}
console.log(avag(arr))
```
#### Remove duplicates from an array.
```
 function removeDup(arr){
  let dup = []
  for(let i=0; i<arr.length; i++){
    if(dup.indexOf(arr[i])===-1){
      dup.push(arr[i])
    }
  }
  return dup
 }
 console.log(removeDup(arr))
```
#### Check if an array contains a specific element.
```
const array = [1, 2, 3, 4, 5];
const element = 3;
const containsElement = array.includes(element);
console.log(containsElement);
```
#### Concatenate two arrays.
```
function concat(arr1,arr2){
  return [...arr1,...arr2]
}
console.log(concat([1,4,3,2],[3,2,4]))
```
#### Sort an array in ascending and descending order.
```
function asceDesc(arr) {
  let asce = arr.slice().sort((a, b) => a - b);
  let desc = arr.slice().sort((a, b) => b - a);

  return { asce, desc };
}

console.log(asceDesc(arr));
```
#### Find the index of the first occurrence of a specific element in an array.
```
function findOcc(arr,val = 3){
  return arr.find(item=>item===val)
}
console.log(findOcc(arr))
```
#### Split an array into chunks of a specified size.
```
function chunkArray(arr, chunkSize) {
  const chunkedArray = [];
  
  for (let i = 0; i < arr.length; i += chunkSize) {
      chunkedArray.push(arr.slice(i, i + chunkSize));
  }
  return chunkedArray;
}

const originalArray = [1, 2, 3, 4, 5, 6, 7, 8];
const chunkSize = 3;
const result = chunkArray(originalArray, chunkSize);
console.log(result);
```
#### Merge two sorted arrays into a single sorted array.
```
function mergeSortedArrays(arr1, arr2) {
  const mergedArray = [];
  let i = 0; // Index for arr1
  let j = 0; // Index for arr2

  while (i < arr1.length && j < arr2.length) {
      if (arr1[i] < arr2[j]) {
          mergedArray.push(arr1[i]);
          i++;
      } else {
          mergedArray.push(arr2[j]);
          j++;
      }
  }

  // If there are remaining elements in arr1, add them to the result.
  while (i < arr1.length) {
      mergedArray.push(arr1[i]);
      i++;
  }

  // If there are remaining elements in arr2, add them to the result.
  while (j < arr2.length) {
      mergedArray.push(arr2[j]);
      j++;
  }

  return mergedArray;
}

const sortedArray1 = [1, 3, 5, 7, 9];
const sortedArray2 = [2, 4, 6, 8, 10];
const mergedArray = mergeSortedArrays(sortedArray1, sortedArray2);
console.log(mergedArray);
```
#### Find the intersection of two arrays (common elements).
```
function findIntersection(arr1, arr2) {
    return arr1.filter(element => arr2.includes(element));
}

const array1 = [1, 2, 3, 4, 5];
const array2 = [3, 4, 5, 6, 7];
const commonElements = findIntersection(array1, array2);
console.log(commonElements); // Output: [3, 4, 5]

```
#### Find the union of two arrays (unique elements).
```
function findUnion(arr1, arr2) {
    const set = new Set([...arr1, ...arr2]);
    return [...set];
}

const array1 = [1, 2, 3, 4, 5];
const array2 = [3, 4, 5, 6, 7];
const unionElements = findUnion(array1, array2);
console.log(unionElements); // Output: [1, 2, 3, 4, 5, 6, 7]
```
#### Rotate an array to the right or left by a specified number of positions.
```
// Rotate an array to the right or left by a specified number of positions.
function rotateRight(arr, positions) {
  let right = [...arr.slice(-positions), ...arr.slice(0, -positions)];
  let left = [...arr.slice(positions), ...arr.slice(0, positions)];
  return {left,right}
}

const originalArray = [1, 2, 3, 4, 5];
const positionsToRotate = 2;
const rotatedArrayRight = rotateRight(originalArray, positionsToRotate);
console.log(rotatedArrayRight);
```
#### Remove a specific element from an array.
```
const array = [1, 2, 3, 4, 5];
const indexToRemove = 2; // Index of the element to remove
array.splice(indexToRemove, 1);
console.log(array); // Output: [1, 2, 4, 5]
```
```
const array = [1, 2, 3, 4, 5];
const elementToRemove = 3;
const newArray = array.filter(item => item !== elementToRemove);
console.log(newArray); // Output: [1, 2, 4, 5]
```
#### Calculate the cumulative sum of elements in an array.
```
function calculateCumulativeSum(arr) {
    let cumulativeSum = 0;
    const cumulativeSumArray = [];

    for (const element of arr) {
        cumulativeSum += element;
        cumulativeSumArray.push(cumulativeSum);
    }
    return cumulativeSumArray;
}
const originalArray = [1, 2, 3, 4, 5];
const cumulativeSum = calculateCumulativeSum(originalArray);
console.log(cumulativeSum); // Output: [1, 3, 6, 10, 15]
```
#### Check if an array is a palindrome.
```


 function palindrome(arr){
    let rev = [...arr].reverse()
    return JSON.stringify(arr)===JSON.stringify(rev)
  }
  console.log(palindrome([1,2,5,2,1]))
```
#### Find the second-largest element in an array.
```
 function findSecondLargest(arr) {
    if (arr.length < 2) {
        return "The array doesn't have a second-largest element.";
    }

    let largest = arr[0];
    let secondLargest = arr[0];

    for (let i = 1; i < arr.length; i++) {
        if (arr[i] > largest) {
            secondLargest = largest;
            largest = arr[i];
        } else if (arr[i] > secondLargest && arr[i] !== largest) {
            secondLargest = arr[i];
        }
    }

    return secondLargest;
}

const array = [1, 5, 2, 7, 3,9, 8];
const secondLargest = findSecondLargest(array);
console.log(secondLargest);
```
#### Merge and sort multiple arrays into one.
```
 function mereg(array1,array2,array3){
    let me = [...array1,...array2,...array3]
    let sort = me.sort((a,b)=>a-b)
    console.log(sort)
  }
  console.log(mereg(array1,array2,array3))
```
#### Count the occurrences of elements in an array.
```
function occ(arr) {
  let occEl = {};
  for (let item of arr) {
      !occEl[item] ? (occEl[item] = 1) : occEl[item]++;
  }
  return occEl;
}

const arr = [1, 2, 2, 3, 1, 4, 2, 5];
console.log(occ(arr));
```
#### int micro 1
```
function mergeAndReplace(A, B) {
  var mergedArray = [];
  for (var i = 0; i < A.length; i++) {
    mergedArray.push(A[i]);
  }
  for (var j = 0; j < B.length; j++) {
    mergedArray.push(B[j]);
  }

  var uniqueArray = [];
  for (var k = 0; k < mergedArray.length; k++) {
    if (uniqueArray.indexOf(mergedArray[k]) === -1) {
      uniqueArray.push(mergedArray[k]);
    }
  }

  var firstOccurrenceIndex = -1;
  for (var m = 0; m < uniqueArray.length; m++) {
    if (uniqueArray[m] === uniqueArray[0]) {
      firstOccurrenceIndex = m;
      break;
    }
  }
  if (firstOccurrenceIndex !== -1) {
    uniqueArray[firstOccurrenceIndex] = 0;
  }

  return uniqueArray;
}

function runTestCases() {
  var testCases = [
    [
      [1, 2, 3, 4],
      [4, 3, 2, 1],
    ],
    [
      [5, 8, 3, 1],
      [2, 4, 6, 9],
    ],
    [
      [2, 4, 6, 8],
      [5, 8, 3, 1],
    ],
    [
      [9, 9, 7, 7],
      [4, 2, 2, 9],
    ],
    [[], []],
    [
      [1, 2, 3],
      [3, 4, 5],
    ],
  ];

  testCases.forEach(function (testCase) {
    console.log(mergeAndReplace(testCase[0], testCase[1]));
  });
}

// Run test cases
runTestCases();

```
```
function mergeAndReplace(A, B) {
  var mergedMap = new Map(); // Use a map to track elements and their first occurrences
  var firstOccurrenceIndex = -1; // Track the index of the first occurrence

  // Merge arrays A and B while removing duplicates and finding the first occurrence
  for (var i = 0; i < A.length; i++) {
    var element = A[i];
    if (!mergedMap.has(element)) {
      // If the element is not in the map
      mergedMap.set(element, mergedMap.size); // Add it to the map with its index
      if (firstOccurrenceIndex === -1) {
        // If this is the first occurrence
        firstOccurrenceIndex = mergedMap.size - 1; // Update the first occurrence index
      }
    }
  }

  for (var j = 0; j < B.length; j++) {
    var element = B[j];
    if (!mergedMap.has(element)) {
      // If the element is not in the map
      mergedMap.set(element, mergedMap.size); // Add it to the map with its index
      if (firstOccurrenceIndex === -1) {
        // If this is the first occurrence
        firstOccurrenceIndex = mergedMap.size - 1; // Update the first occurrence index
      }
    }
  }

  // Construct the merged array and replace the first occurrence with 0
  var mergedArray = [];
  mergedMap.forEach(function (value, key) {
    if (value === firstOccurrenceIndex) {
      // If this is the first occurrence
      mergedArray.push(0); // Replace it with 0
    } else {
      mergedArray.push(key); // Otherwise, add the element as is
    }
  });

  return mergedArray;
}

// Test cases
function runTestCases() {
  var testCases = [
    [
      [5, 8, 3, 1],
      [2, 4, 6, 9],
    ],
    [
      [2, 4, 6, 8],
      [5, 8, 3, 1],
    ],
    [
      [9, 9, 7, 7],
      [4, 2, 2, 9],
    ],
    [[], []],
    [
      [1, 2, 3],
      [3, 4, 5],
    ],
  ];

  testCases.forEach(function (testCase) {
    console.log(mergeAndReplace(testCase[0], testCase[1]));
  });
}

// Run test cases
runTestCases();

```

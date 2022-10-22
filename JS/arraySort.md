# Binary Seach
``` js
 binarySearch(arr, value) {
  let high = arr.length - 1;
  let low = 0;
  let mid = 0;

  while (low <= high) {
    mid = Math.floor((high + low) / 2);
    if (counters[mid] == value) {
      return counters[mid];
    } else if (counters[mid] < value) {
      low = mid + 1;
    } else {
      high = mid - 1;
    }
  }   
  return null;
} 
```
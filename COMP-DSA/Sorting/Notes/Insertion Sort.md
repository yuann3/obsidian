Insertion sort is one sorting algorithm used to sort data in different data structures. It is one of the simplest sorting algorithms that ***works best when the data size is small***
![[Pasted image 20240621150742.png]]


```cpp
vector<int> insertionSort(vector<int>& arr) {
    for (int i = 1; i < arr.size(); i++) {
        int j = i - 1;
        while (j >= 0 && arr[j + 1] < arr[j]) {
            int tmp = arr[j + 1];
            arr[j + 1] = arr[j];
            arr[j] = tmp;
            j--;
        }
    }
    return arr;
}
```

> As long as there is a way to compare two values, this algorithm will work on any data type.

> So, why not just use recursion? Recursion is not advantageous over an iterative sorting solution. The recursive approach typically requires more time and memory, while the iterative implementation is more intuitive.

## Stability

Stability in a sorting algorithm refers to the relative order of the elements after the sorting is done. Take `[7,3,7]` for example. There are two 7s, one at the `0th` index and the other at the `2nd` index. We know that the relative order of these two 7s will stay the same since 3 will swap with the 7 at the `0th` index and then the while loop will never be implemented.

This is called a **stable** sorting algorithm. Insertion sort is stable, meaning that it is guarenteed that the relative order will remain the same. In an unstable sorting algorithm, this is not guarenteed and we shall see why in a few chapters.

## Time Space Complexity

In the best case, insertion sort on an array of size n has $O(n)$ time complexity, as the array is already sorted. In the worst case, with elements sorted in reverse order, the time complexity is $O(n^2)$ due to the nested loops.
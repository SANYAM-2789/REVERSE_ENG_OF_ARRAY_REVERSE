# REVERSE_ENG_OF_ARRAY_REVERSE
Reversing an array means rearranging the elements of the array such that the first element becomes the last, the second element becomes the second to last, and so on. This operation can be efficiently performed using a two-pointer approach. Here's a detailed explanation of how the reverseArray function works:

Function Declaration and Definition
The function reverseArray is declared in the header file reverse.h and defined in the source file reverse.cpp.

reverse.h
cpp
Copy code
#ifndef REVERSE_H
#define REVERSE_H

#include <vector>

void reverseArray(std::vector<int>& arr);

#endif
This header file declares the reverseArray function which takes a reference to a std::vector<int> as its parameter.
reverse.cpp
cpp
Copy code
#include "reverse.h"

void reverseArray(std::vector<int>& arr) {
    int n = arr.size();
    for(int i = 0; i < n / 2; ++i) {
        std::swap(arr[i], arr[n - 1 - i]);
    }
}
This source file defines the reverseArray function.
Detailed Explanation of the Reverse Logic
1. Get the Size of the Array
cpp
Copy code
int n = arr.size();
The size of the array arr is stored in the variable n.
2. Loop Through the First Half of the Array
cpp
Copy code
for(int i = 0; i < n / 2; ++i) {
A loop runs from i = 0 to i < n / 2. This ensures that only the first half of the array is processed, as swapping elements in the first half with elements in the second half will reverse the entire array.
3. Swap the Elements
cpp
Copy code
std::swap(arr[i], arr[n - 1 - i]);
For each index i in the first half of the array, the element at position i (arr[i]) is swapped with the element at position n - 1 - i (arr[n - 1 - i]).
The std::swap function efficiently swaps the values of the two elements.
Example Walkthrough
Consider an example array: [1, 2, 3, 4, 5].

Initial State:

Array: [1, 2, 3, 4, 5]
Size n: 5
Halfway point: n / 2 = 2
First Iteration (i = 0):

Swap arr[0] and arr[4]:
std::swap(arr[0], arr[4]) swaps 1 and 5.
Array becomes: [5, 2, 3, 4, 1]
Second Iteration (i = 1):

Swap arr[1] and arr[3]:
std::swap(arr[1], arr[3]) swaps 2 and 4.
Array becomes: [5, 4, 3, 2, 1]
Loop Ends:

The loop ends after i = 1 because i < n / 2 is no longer true for i = 2.
Final State:

The array is now reversed: [5, 4, 3, 2, 1]

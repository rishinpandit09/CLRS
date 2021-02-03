# Exercise 2.3 

### Exercise2.3-1 

Using Figure 2.4 as a model, illustrate the operation of merge sort on the array A = [3, 41, 52, 26, 38, 57, 9, 49]. 

Ans: Draw the diagram as shown in the book 

### Exercise2.3-2 

Rewrite the MERGE procedure so that it does not use sentinels, instead stopping once either array L or R has had all its elements copied back to A and then copying the remainder of the other array back into A. 

Ans: 

Mergesort Code 

 

### Exercise2.3-3 

Use mathematical induction to show that when n is an exact power of 2, the solution of the recurrence  

T(n) { 2    if n = 2 
          2T(n/2) + n  if n = 2^k, k>1 

Is T(n) = nlg(n) 

Ans:  

 

### Exercise 2.3-4 

Insertion sort can be expressed as a recursive procedure as follows. In order to sort A[1..n], we recursively sort A[1..n -1] and then insert A[n] into the sorted array A[1..n - 1]. Write a recurrence for the running time of this recursive version of insertion sort. 

Ans 

There are two steps in this recursive sorting algorithm: 

Sort the sub-array A[1..n-1]A[1..n−1] 

Insert A[n]A[n] into the sorted sub-array from step 1 in proper position 

For n = 1n=1, step 1 doesn’t take any time as the sub-array is an empty array and step 2 takes constant time, i.e. the algorithm runs in \Theta(1)Θ(1) time. 

For n > 1n>1, step 1 again calls for the recursion for n - 1n−1 and step 2 runs in \Theta(n)Θ(n) time. 

Let us first write the pseudocode for auxiliary procedure required to insert A[n]A[n] into the sorted array as follows … 

Insert(A, k) 

Key = A[k] 

i= k-1 

While(i>0 && A[i] > key 

A[i + 1] = A[i] 

i = i - 1  

A[i+1] = key 

 

RecurssiveInsertSort(A,n) 

If n>1 

RecurssiveInsertSort(A,n-1) 

Insert(A,n) 

 

### Exercise 2.3-5 
Referring back to the searching problem (see Exercise 2.1-3), observe that if the sequence A is sorted, we can check the midpoint of the sequence against v and eliminate half of the sequence from further consideration. Binary search is an algorithm that repeats this procedure, halving the size of the remaining portion of the sequence each time. Write pseudocode, either iterative or recursive, for binary search. Argue that the worst-case running time of binary search is Θ(lg n). 

Ans: 

Binary Search  
Iterative  

Algorithm 

Low = Array[0](first elemnt of the array) 

High = Array[A.length](last element of the array) 

While Low < High 

   Mid = (Low + High)/2 

   If v == Mid 

      Return Mid 

   Elseif v>Array[Mid] 

      Low = Mid + 1 

   Else 

       High = Mid – 1 

return NIL 

RecursiveBinarySearch(Array, Low, High)  Algorithm  

If Low>High 

   Return NIL 

Mid = (Low + High)/2 

If v == Array[Mid] 

  Return Mid 

If v>Array[Low] 

   RecursiveBinarySearch(Array,Mid+1,High) 

Else 

   RecursiveBinarySearch(Array, Low, Mid-1) 

 

in worst case, i.e. when v is not at all present in Array, we need to search over the whole array to return NIL. In other words, we need to repeatedly divide the array by 2 and check either half for v. So the running time is nothing but how many times the input size can be divided by 2, i.e. Lgn. 

 

### Exercise2.3-6 

Observe that the while loop of lines 5 - 7 of the INSERTION-SORT procedure in Section 2.1 uses a linear search to scan (backward) through the sorted subarray A[1..j - 1]. Can we use a binary search (see Exercise 2.3-5) instead to improve the overall worst-case running time of insertion sort to Θ(n lg n)? 

Ans: 

Each time the while loop of lines 5-7 of INSERTION-SORT scans backward through the sorted array A[1..j - 1]A[1..j−1]. The loop not only searches for the proper place for A[j]A[j], but it also moves each of the array elements that are bigger than A[j]A[j] one position to the right (line 6). These movements takes \Theta(j)Θ(j) time, which occurs when all the j - 1j−1 elements preceding A[j]A[j] are larger than A[j]A[j]. The running time of using binary search to search is Θ(lgj), which is still dominated by the running time of moving element Θ(j). 

 
### Exercise2.3-7 

Describe a Θ(nlgn)-time algorithm that, given a set S of n integers and another integer x, determines whether or not there exist two elements in S whose sum is exactly x. 

Ans: 

Time taken to sort S is Θ(nlgn)  

Time taken to search each element using Binary search is Θ(lgn) 

 

The time complexity of the algorithm is  

Θ(nlgn) +  n.Θ(lgn) = Θ(nlgn)  

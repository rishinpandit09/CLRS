# Exercise 2.2 

 

## Exercise 2.2-1 

Express the function n^3/1000 - 100n^2 – 100n + 3 in terms of Θ-notation. 

Ans : 

Applying rule to each of these, this will equal Θ(max(n 3 , n2 , n, 1)). Now we can apply rule (4) to see that1 Θ(1) < Θ(n) < Θ(n 2 ) < Θ(n 3 ). 
So Θ(max(n 3 , n2 , n, 1)) = Θ(n 3 ). 

 


## Exercise2.2-2 

Consider sorting n numbers stored in array A by first finding the smallest element of A and exchanging it with the element in A[1]. Then find the second smallest element of A, and exchange it with A[2]. Continue in this manner for the first n - 1 elements of A. Write pseudocode for this algorithm, which is known as selection sort. What loop invariant does this algorithm maintain? Why does it need to run for only the first n - 1 elements, rather than for all n elements? Give the best-case and worst-case running times of selection sort in Θ- notation. 

Ans: 

For i = 0 to i < A.length-1  

   Min_index = i  

   For j = i + 1 to j<A.length  

      If A[j]<A[i]  

        Min_index = j 

If (Min_index != I)  

   Swap A[i] with A[j] 

Selection Sort requires two nested for loops to complete itself, one for loop is in the function selectionSort, and inside the first loop we are making a call to another function Min_index, which has the second(inner) for loop. 

Hence for a given input size of n, following will be the time and space complexity for selection sort algorithm: 

Worst Case Time Complexity [ Big-O ]: O(n2) 

Best Case Time Complexity [Big-omega]: O(n2) 

Average Time Complexity [Big-theta]: O(n2) 

Space Complexity: O(1) 

 


## Exercise2.2-3 

Consider linear search again (see Exercise 2.1-3). How many elements of the input sequence need to be checked on the average, assuming that the element being searched for is equally likely to be any element in the array? How about in the worst case? What are the average-case and worst-case running times of linear search in Θ-notation? Justify your answers. 

Ans: 

If the element is present in the sequence, half of the elements are likely to be checked before it is found in the average case. In the worst case, all of them will be checked. That is, n/2 checks for the average case and n for the worst case. Both of them are Θ(n). 

 

## Exercise 2.2-4 

How can we modify almost any algorithm to have a good best-case running time? 

Ans:  

You can modify any algorithm to have a best case time complexity of O(n) by adding a special case, that if the input matches this special case 

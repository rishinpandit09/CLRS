# PROBLEMS


### 2-1 Insertion Sort on Small Arrays in Merge Sort

Although merge sort runs in ‚.n lg n/ worst-case time and insertion sort runs
in ‚.n2/ worst-case time, the constant factors in insertion sort can make it faster
in practice for small problem sizes on many machines. Thus, it makes sense to
coarsen the leaves of the recursion by using insertion sort within merge sort when subproblems become sufficiently small. Consider a modification to merge sort in
which n=k sublists of length k are sorted using insertion sort and then merged
using the standard merging mechanism, where k is a value to be determined.

## a. Show that insertion sort can sort the n=k sublists, each of length k, in ‚.nk/worst-case time.
### Ans-
To sort a list of length k using insertion sort, the worst time calculated is  Θ(k^2). Hence, for n/k sublists, the worst case is Θ(k^2.n/k)=Θ(kn).

## b. Show how to merge the sublists in Θ(n lg(n/k)) worst-case time.
### Ans-
Length of each substring = k and number of such substrings is n/k. To get a single merged list, we need to take two such lists at a time and merge themm, then repeat the same process. By this, we will get lg(n/k) steps. Also we compare n elements in each step. Thus the worst time becomes Θ(n lg(n/k)).

## c. Given that the modified algorithm runs in Θ(nk+nlg⁡(n/k))\Theta(nk + n\lg(n / k))Θ(nk+nlg(n/k)) worst-case time, what is the largest value of kkk as a function of nnn for which the modified algorithm has the same running time as standard merge sort, in terms of Θ\ThetaΘ-notation?
### Ans-
Assuming k=Θ(lgn),
     Θ(nk+nlg(n/k))=Θ(nk+nlgn−nlgk)
                   =Θ(nlgn+nlgn−nlg(lgn))
                   =Θ(2nlgn−nlg(lgn))
                   =Θ(nlgn)
        
## d. How should we choose kkk in practice?\
### Ans-
We figure out when insertion sort beats merge sort and then pick that number for k.

## 2-2 Correctness of bubblesort

Bubblesort is a popular, but inefficient, sorting algorithm. It works by repeatedly swapping adjacent elements that are out of order.
BUBBLESORT(A)
    for i = 1 to A.length - 1
        for j = A.length downto i + 1
            if A[j] < A[j - 1]
                exchange A[j] with A[j - 1]

## a. Let A′A'A′ denote the output of BUBBLESORT(A)\text{BUBBLESORT}(A)BUBBLESORT(A) To prove that BUBBLESORT\text{BUBBLESORT}BUBBLESORT is correct, we need to prove that it terminates and that
## A′[1]≤A′[2]≤⋯≤A′[n]                                                                                            (2.3)
## where n=A.lengthn = A.lengthn=A.length. In order to show that BUBBLESORT\text{BUBBLESORT}BUBBLESORT actually sorts, what else do we need to prove?
### Ans-
The other thing that we have to prove is that A′ consists of the elements in AAA but in sorted order.

## b. State precisely a loop invariant for the for loop in lines 2–4, and prove that this loop invariant holds. Your proof should use the structure of the loop invariant proof presented in this chapter.
### Ans-
### Loop invariant:
At the start of each iteration of the for loop of lines 2-4, the subarray A[j..n] consists of the elements originally in A[j..n] before entering the loop but possibly in a different order and the first element A[j] is the smallest among them.
### Initialization:
Initially the subarray contains only the last element A[n], which is trivially the smallest element of the subarray.
### Maintenance:
In every step we compare A[j]A[j]A[j] with A[j−1] and make A[j−1] the smallest among them. After the iteration, the length of the subarray increases by one and the first element is the smallest of the subarray.
### Termination:
The loop terminates when j=i. According to the statement of loop invariant, A[i] is the smallest among A[i..n] and A[i..n] consists of the elements originally in A[i..n] before entering the loop.

## c. Using the termination condition of the loop invariant proved in part (b), state a loop invariant for the for loop in lines 1–4 that will allow you to prove inequality (2.3). Your proof should use the structure of the loop invariant proof presented in this chapter.
### Ans-
### Loop invariant:
At the start of each iteration of the for loop of lines 1-4, the subarray A[1..i−1] consists of the i−1 smallest elements in A[1..n] in sorted order. A[i..n] consists of the n−i+1 remaining elements in A[1..n].
### Initialization:
Initially the subarray A[1..i−1] is empty and trivially this is the smallest element of the subarray.
### Maintenance:
From part (b), after the execution of the inner loop, A[i] will be the smallest element of the subarray A[i..n]. And in the beginning of the outer loop, A[1..i−1] consists of elements that are smaller than the elements of A[i..n], in sorted order. So, after the execution of the outer loop, subarray A[1..i] will consists of elements that are smaller than the elements of A[i+1..n], in sorted order.
### Termination:
The loop terminates when i=A.lengthi = A.lengthi=A.length. At that point the array A[1..n] will consists of all elements in sorted order.

## d. What is the worst-case running time of bubblesort? How does it compare to the running time of insertion sort?
### Ans-
The worst case running time of Bubble Sort is O(n^2). For Insertion Sort, the worst case running time is also O(n^2), although it also shows a running time of O(n).


## 2-3 Correctness of Horner's Rule
The following code fragment implements Horner's rule for evaluating a polynomial
P(x) = (k=0 to n)∑ ak.x^k 
     = a0+x(a1+x(a2+.....+x(an-1 +xan).....)),
given the coefficients a0,a1,…,an and a value for x:
y = 0
for i = n downto 0
    y = a[i] + x * y
## a. In terms of Θ-notation, what is the running time of this code fragment for Horner's rule?
### Ans-
The running time of this snippet is Θ(n).

## b. Write pseudocode to implement the naive polynomial-evaluation algorithm that computes each term of the polynomial from scratch. What is the running time of this algorithm? How does it compare to Horner’s rule? 
### Ans-
NAIVE-HORNER()
    y = 0
    for k = 0 to n
        temp = 1
        for i = 1 to k
            temp = temp * x
        y = y + a[k] * temp
It is slower because of the nested loop, and the running time is Θ(n2).

## c. Consider the following loop invariant:
## At the start of each iteration of the for loop of lines 2–3,
           y=(k=0 to (n-(i+1)))∑(ak+i+1)x^k
## Interpret a summation with no terms as equaling 0. Following the structure of the loop invariant proof presented in this chapter, use this loop invariant to show that, at termination, y = (k=0 to n)∑akx^k
### Ans- 
### Initialization:
It is pretty trivial, since the summation has no terms which implies y=0
### Maintenance:
By using the loop invariant, in the end of the iii-th iteration, we have
          y = (k=0 to n-i) ∑ ak+ix^k
### Termination:
The loop terminates at i=−1i = -1i=−1. If we substitute,
          y = (k=0 to n-i-1) ∑ ak+i+1x^k
            = (k=0 to n) ∑ akx^k
## d. Conclude by arguing that the given code fragment correctly evaluates a polynomial characterized by the coefficients a0, a1, a2,...., an
### Ans-
The invariant of the loop is a sum that equals a polynomial with the given coefficients.










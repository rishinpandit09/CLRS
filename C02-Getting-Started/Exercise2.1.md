# Exercise 2.1

### Exercise 2.1-1 

Using Figure 2.2 as a model, illustrate the operation of INSERTION-SORT on the array A = [31, 41, 59, 26, 41, 58]. 

Ans: 

 

 

### Exercise2.1-2 

Rewrite the INSERTION-SORT procedure to sort into nonincreasing instead of nondecreasing order. 

Ans: 

For i = 2 to length[A] (i=2 means second element of the array) 

   Key = A[j] 

    // Insert A[j] into the sorted sequence A[1 ….. j-1] 

    i= j-1 

    While i > 0 and A[i]<key 

          A[i+1] = A[i] 

          i = i-1 

 A[i+1] = key 
 
 
 

### Exercise 2.1-3 

 

Consider the searching problem: 

Input: A sequence of n numbers A = [a1, a2, . . . , an] and a value v. 

Output: An index i such that v = A[i] or the special value NIL if v does not appear in A. 

Write pseudocode for linear search, which scans through the sequence, looking for v. Using a loop invariant, prove that your algorithm is correct. Make sure that your loop invariant fulfills the three necessary properties. 

Ans: 

Linear Search Algorithm 

For i = 1 to length[A]  

    If v = A[i] 

       Return i  

     Return nil 

 

### Exercise 2.1-4 

Consider the problem of adding two n-bit binary integers, stored in two n-element arrays A and B. The sum of the two integers should be stored in binary form in an (n + 1)-element array C. State the problem formally and write pseudocode for adding the two integers. 

Ans: 

A.length = n; 

B.length = n; 

C.length = n+1; 

Carry = 0 

For i = n-1 to 0 

C[i+1] = (A[i] + B[i] + Carry) mod 2  

Carry = (A[i] + B[i] + Carry) / 2  

C[0] = Carry  

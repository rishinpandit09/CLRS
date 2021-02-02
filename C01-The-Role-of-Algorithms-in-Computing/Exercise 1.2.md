# Exercise 1.2 

### Exercise 1.2.-1 

Give an example of an application that requires algorithmic content at the application level, and discuss the function of the algorithms involved. 

Ans: Google Maps require a lot of algorithmic content to find the shortest distance between two points while keeping the other constrains 

 

 
### Exercise 1.2-2 

Suppose we are comparing implementations of insertion sort and merge sort on the same machine. For inputs of size n, insertion sort runs in 8n^2 steps, while merge sort runs in 64nlgn steps. For which values of n does insertion sort beat merge sort? 

Ans: 8n^2 < 64nlgn 

n < 8lgn 

2^(n/8) < n 

Therefore, for 2 < n <= 43  insertion sort beats merge sort 

 

### Exercise 1.2-3 

What is the smallest value of n such that an algorithm whose running time is 100n^2 runs faster than an algorithm whose running time is 2^n on the same machine? 

A (quadratic time complexity) will run much faster than B (exponential time complexity) for very large values of n. Let’s start checking from n=1 and go up for values of n which are power of 2. 

n=1⇒ 100×1^2 = 100 > 2^1   

n=2⇒ 100×2^2 = 400 > 2^2   

n=4⇒ 100×4^2 = 1600 > 2^4   

n=8⇒ 100×8^2 = 6400 > 2^8   

n=16⇒ 100×16^2 = 25600 < 2^16 

Somewhere between 8 and 16, A starts to run faster than B. Let’s do what we were doing but now we are going to try middle value of the range, repeatedly (binary search). 

n=8+16/ 2 = 12⇒100×12^2=14400 > 2^12   

n=12+16/ 2=14⇒100×14^2=19600 > 2^14   

n=14+16/ 2=15⇒100×15^2=22500 < 2^15 

So, at n=15, A starts to run faster than B. 

 

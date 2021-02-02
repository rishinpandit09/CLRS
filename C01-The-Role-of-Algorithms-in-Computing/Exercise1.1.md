##Exercise 1.1-1 

Give a real-world example in which one of the following computational problems appears: sorting, determining the best order for multiplying matrices, or finding the convex hull. 

Ans:  

Sorting: The contacts in the phonebook are sorted alphabetically.  

Matrices: Matrices contain tabular data that can be used to store 3d points, financial data. The real world application is graphics rendering, video rendering stock exchange etc. 

 

Convex hull:  The problem of finding convex hulls finds its practical applications in pattern recognition, image processing, statistics, geographic information system, game theory, construction of phase diagrams, and static code analysis by abstract interpretation. It also serves as a tool, a building block for a number of other computational-geometric algorithms such as the rotating calipers method for computing the width and diameter of a point set. also application in CV. 

 

##Exercise 1.1-2 

Other than speed, what other measures of efficiency might one use in a real-world setting? 

Memory usage and resource utilization (network, database) are good answers. 

Exercise 1.1-3 

Select a data structure that you have seen previously, and discuss its strengths and limitations. 

 

Stack: 

Helps you to manage the data in a Last In First Out(LIFO) method which is not possible with Linked list and array. 

When a function is called the local variables are stored in a stack, and it is automatically destroyed once returned. 

A stack is used when a variable is not used outside that function. 

It allows you to control how memory is allocated and deallocated. 

Stack automatically cleans up the object. 

Not easily corrupted 

Variables cannot be resized. 

Linked List: 

It does not need sequential space in memory 

We can insert a new element at any place 

Random access is O(n) 

It takes additional memory for the links 

 

 

##Exercise 1.1-4 

How are the shortest-path and traveling-salesman problems given above similar? How are they different? 

They are similar, because each of then has to walk a graph and find a path in them. 

The difference is the constraint on the solution. The shortest-path requires just a path between two points, while the traveling salesman requires a path between more points that returns to the first point. 

 
##Exercise 1.1-5 

Come up with a real-world problem in which only the best solution will do. Then come up with one in which a solution that is "approximately" the best is good enough. 

Sorting of a list (only the best solution will do, nearly sorted is not acceptable) 

Finding a shortest path in a city map ( approximately will do, a couple of meters don’t matter here) 

 
 

 
 

 

 
 

 

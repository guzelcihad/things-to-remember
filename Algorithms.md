# Algorithmic Paradigms
* Brute Force
* Greedy Algorithms
* Divide and Conquer
* Dynamic Programming

## Brute Force
Let’s start off our discussion on algorithms with the most straightforward and exhaustive option—the brute force approach to solving a problem. This method requires us to go through all the possible solutions to the problem we are meaning to solve. For instance, if we have an array of integers and we want to find the minimum, maximum, or a certain element in that array, the brute force approach requires us to go through all the elements to find that specific element. There are no shortcuts and no performance improvements at this stage.
<br>
Even though this approach of solving problems is the most inefficient one, it might be the first one that pops into our heads. Also, the good thing about the brute force method is that if a solution to our problem exists, we are guaranteed to find it this way. Once we have a way to go about solving the problem, we can focus on making the solution more efficient.

## Dynamic Programming
Dynamic Programming (DP) is an algorithmic technique for solving an optimization problem by breaking it down into simpler subproblems and utilizing the fact that the optimal solution to the overall problem depends upon the optimal solution to its subproblems.

# Characteristics of Dynamic Programming
> Overlapping Subproblems

Subproblems are smaller versions of the original problem. Any problem has overlapping sub-problems if finding its solution involves solving the same subproblem multiple times. Take the example of the Fibonacci numbers; to find the fib(4)
we need to break it down into the foloowing sub-problems.

We can clearly see the overlapping subproblem pattern here, as fib(2) has been evaluated twice and fib(1) has been evaluated three times.

### Dynamic Programming Methods

> Top-down with Memoization

In this approach, we try to solve the bigger problem by recursively finding the solution to smaller sub-problems. Whenever we solve a sub-problem, we cache its result so that we don’t end up solving it repeatedly if it’s called multiple times. Instead, we can just return the saved result. This technique of storing the results of already solved subproblems is called Memoization.

We’ll see this technique in our example of Fibonacci numbers. First, let’s see the non-DP recursive solution for finding the nth Fibonacci number:

> Bottom-up with Tabulation

Tabulation is the opposite of the top-down approach and avoids recursion. In this approach, we solve the problem “bottom-up” (i.e. by solving all the related sub-problems first). This is typically done by filling up an n-dimensional table. Based on the results in the table, the solution to the top/original problem is then computed.

Tabulation is the opposite of Memoization, as in Memoization we solve the problem and maintain a map of already solved sub-problems. In other words, in memoization, we do it top-down in the sense that we solve the top problem first (which typically recurses down to solve the sub-problems).

# Sorting
Q1: Why stability matters in sorting?
> it can matter when you're sorting objects. If you want to sort based on one field, and then sort based on a second field without undoing the results of the first sort, you have to use a stable sort algorithm.

> For example, let's say you sort employees by last name, and this is the result:
Kind | Version
--- | --- |
John Doe  | 35 | 283 |
Mary Smith | 28 | 283 |
Alan Smith | 35 | 283 |
Jane Smith  | 55 | 283 |
Bill Wilson   | 35 | 283 |

> Now you want to sort by age, and you want employees with duplicate ages to remain sorted by last name. You have to use a stable sort algorithm to make that happen:

Name                  Age
Mary Smith          28
John Doe             35
Alan Smith           35
Bill Wilson            35
Jane Smith           55

> If you don't use a stable sort algorithm, then the three employees with age 35 might not be sorted by last name. So it can make a difference. It will depend on the type of data you're sorting, and what you're trying to do.
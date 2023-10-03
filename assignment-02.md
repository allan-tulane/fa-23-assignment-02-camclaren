# CMPS 2200 Assignment 2

**Name:** Cameron McLaren

In this assignment we'll work on applying the methods we've learned to analyze recurrences, and also see their behavior
in practice. As with previous
assignments, some of of your answers will go in `main.py` and `test_main.py`. You
should feel free to edit this file with your answers; for handwritten
work please scan your work and submit a PDF titled `assignment-02.pdf`
and push to your github repository.


1. Derive asymptotic upper bounds of work for each recurrence below.
  * $W(n)=2W(n/3)+1$

W(n) is leaf dominated. Therefore, you need to find the work at the end leaves.
height of tree: log3(n)
number of nodes at i level: 2^i

Hence, the number of nodes at level log3(n) is 2^log3(n)

The work upper bound is O(n^log3(2))

  
  * $W(n)=5W(n/4)+n$

W(n) is leaf dominated. Therefore, you need to find the work at the end leaves.

height of tree: log4(n)
number of nodes at i level: 5^i

5^log4(n) belongs to O(n^log4(5)), which is the upper bound for the work.


  * $W(n)=7W(n/7)+n$

W(n) is balanced. Therefore, you need to multiply the maximum cost with the number of levels.

maximum cost: n, number of levels: log7(n)

The work upper bound is O(nlog7(n))


  * $W(n)=9W(n/3)+n^2$

W(n) is balanced. Therefore, you need to multiply the maximum cost with the number of levels.

maximum cost: n^2, number of levels: log3(n)

The work upper bound is O((n^2)log3n)


  * $W(n)=8W(n/2)+n^3$

W(n) is balanced. Therefore, you need to multiply the maximum cost with the number of levels.

maximum cost: n^3, number of levels: lg(n)

The work upper bound is O(n^3 * lg(n))


  * $W(n)=49W(n/25)+n^{3/2}\log n$

W(n) is root dominated. Therefore, the work of the function is the work of the root.

The work of the root is n^(3/2)(log(n)), therefore the work upper bound of the function is O(n^(3/2)(log(n))).


  * $W(n)=W(n-1)+2$

W(n) is leaf dominated, which means that the work is the same as the work at the end leaves.

height of tree: 2^i
number of nodes at i level: 2^lg(n) = n

Hence, the work upper bound of the function is O(n)

  * $W(n)= W(n-1)+n^c$, with $c\geq 1$

W(n) is balanced. Therefore, you need to multiply the maximum cost with the number of levels.

maximum cost: n^c, number of levels: n

The work upper bound is O(n^(c+1))


  * $W(n)=W(\sqrt{n})+1$

W(n) is balanced. Therefore, you need to multiply the maximum cost with the number of levels.

maximum cost: 1, number of levels: lg(lg(n))

The work upper bound is O(lg(lg(n)))


2. Suppose that for a given task you are choosing between the following three algorithms:

  * Algorithm $\mathcal{A}$ solves problems by dividing them into
      five subproblems of half the size, recursively solving each
      subproblem, and then combining the solutions in linear time.
  
  W(n) = 5W(n/2) + n

  W(n) is leaf dominated. Therefore, the runtime is the number of the leaves.

  height of tree: lg(n)
  number of nodes at i level: 5^i

  5^lg(n) belongs to O(n^lg(5)), which is the upper bound for the runtime.
     
  * Algorithm $\mathcal{B}$ solves problems of size $n$ by
      recursively solving two subproblems of size $n-1$ and then
      combining the solutions in constant time.
  
  W(n) = 2W(n-1) + 1

  W(n) is leaf dominated. Therefore, the runtime is the number of the leaves.

  height of tree: n
  number of nodes at i level: 2^i

  2^n belongs to O(2^n), which is the upper bound for the runtime.
    
  * Algorithm $\mathcal{C}$ solves problems of size $n$ by dividing
      them into nine subproblems of size $n/3$, recursively solving
      each subproblem, and then combining the solutions in $O(n^2)$
      time.
  
  W(n) = 9W(n/3) + n^2

  W(n) is balanced, thus the runtime is the product of the maximum cost with the number of levels.

  maximum cost: n^2
  number of levels: log3(n)

  Therefore, the runtime has an upper bound of O(n^2(log3(n)))

    What are the asymptotic running times of each of these algorithms?

    [see above]

    Which algorithm would you choose?

    We can eliminate Algorithm B because it has an exponential upper bound, which is the worst of the three. Now, we just have to compare Algorithm A and C.Algorithm C has an upper bound runtime of O(n^lg(5)), and if you graph it alongside the upper bound runtime of Algorithm A, O(n^2(lg(n))), you can see that Algorithm C is more efficient.



3. Now that you have some practice solving recurrences, let's work on
  implementing some algorithms. In lecture we discussed a divide and
  conquer algorithm for integer multiplication. This algorithm takes
  as input two $n$-bit strings $x = \langle x_L, x_R\rangle$ and
  $y=\langle y_L, y_R\rangle$ and computes the product $xy$ by using
  the fact that $xy = 2^{n/2}x_Ly_L + 2^{n/2}(x_Ly_R+x_Ry_L) +
  x_Ry_R.$ Use the
  stub functions in `main.py` to implement Karatsaba-Ofman algorithm algorithm for integer
  multiplication: a divide and conquer algorithm that runs in
  subquadratic time. Then test the empirical running times across a
  variety of inputs in `test_main.py` to test whether your code scales in the manner
  described by the asymptotic runtime. Please refer to Recitation 3 for some basic implementations, and Eqs (7) and (8) in the slides https://github.com/allan-tulane/cmps2200-slides/blob/main/module-02-recurrences/recurrences-integer-multiplication.ipynb
 
 



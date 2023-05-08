Download Link: https://assignmentchef.com/product/solved-ve492-homework-5
<br>
<h1>Question 1: Campus Layout</h1>

You are asked to determine the layout of a new, small college. The campus will have four structures: an administration structure (A), a bus stop (B), a classroom (C), and a dormitory (D). Each structure (including the bus stop) must be placed somewhere on the grid shown below.

The layout must satisfy the following constraints:

<ol>

 <li>The bus stop (B) must be adjacent to the road. ii. The administration structure (A) and the classroom (C) must both be adjacent to the bus stop (B). iii. The classroom (C) must be adjacent to the dormitory (D).</li>

 <li>The administration structure (A) must not be adjacent to the dormitory (D). v. The administration structure (A) must not be on a hill.</li>

 <li>The dormitory (D) must be on a hill or adjacent to the road. vii. All structures must be in different grid squares.</li>

</ol>

Here, <em>adjacent </em>means that the structures must share a grid edge, not just a corner.

<em>We recommend you work out the solutions to the following questions on a sheet of scratch paper, and then enter your results below.</em>

<h2>Part 1: Unary Constraints</h2>

<ul>

 <li>Which of the constraints above are unary constraints?

  <ol>

   <li>i</li>

   <li>ii</li>

   <li>iii</li>

   <li>iv</li>

   <li>v</li>

   <li>vi</li>

   <li>vii</li>

   <li>None of the above</li>

  </ol></li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>ABCD</em></strong>

<ul>

 <li>Write the domains of all variables after unary constraints have been applied.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1,1)(1,2)B(1,1)C(1,1)(1,2)D(1,1)(1,2)</em></strong>

<h2>Part 2:Arc Consistency</h2>

Let’s start from the table above (the answer to Part 1) and enforce arc consistency. Initially, the queue contains all arcs (in alphabetical order).

Let’s examine what happens when enforcing A→B. After enforcing unary constraints, the domains of A and B are:

<ul>

 <li>Which of the following contains the correct domains after enforcing A→B? Pay attention to which variable’s domain changes and which side of the arc it’s on.

  <ol>

   <li>i</li>

   <li>ii</li>

   <li>iii</li>

   <li>iv</li>

  </ol></li>

 <li>Starting from the answer to Part 1 (in which unary constraints are enforced), write the domains of all variables after A→B is enforced.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1,1)(1,2)B(1,1)C(1,1)(1,2)D(1,1)(1,2)</em></strong>

<ul>

 <li>You should verify that enforcing consistency for A→C, A→D, B→A, B→C, B→D, and C→A do not change the domains of any variables. After enforcing these arcs, the next is C→B.</li>

</ul>

Continuing from the previous parts, write the domains of all variables after C→B is enforced.

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1,1)(1,2)B(1,1)C(1,1)(1,2)D(1,1)(1,2)</em></strong>

<ul>

 <li>What arcs got added to the queue while enforcing C→B? Remember that the queue contained C→D, D→A, D→B, and D→C prior to enforcing C→B.

  <ol>

   <li>A→B</li>

   <li>A→C</li>

   <li>A→D</li>

   <li>B→A</li>

   <li>B→C</li>

   <li>B→D</li>

   <li>C→A</li>

   <li>C→B</li>

   <li>C→D</li>

   <li>D→A</li>

   <li>D→B</li>

   <li>D→C</li>

   <li>None</li>

  </ol></li>

 <li>Continuing from the previous parts, select the domains of all variables after enforcing arc consistency until the queue is empty. Remember that the queue currently contains C→D, D→A, D→B, D→C, and any arcs that were added while enforcing C→B.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1,1)(1,2)B(1,1)C(1,1)(1,2)D(1,1)(1,2)</em></strong>

<h2>Part 3: Search withArc Consistency</h2>

(h) If arc consistency had resulted in all domains having a single value left, we would have already found a solution. Similarly, if it had found that any domain had no values left, we would have already found that no solution exists. Unfortunately, this is not the case in our example (as you should have found in the previous part). To solve the problem, we need to start searching. Use the MRV (minimum remaining values) heuristic to choose which variable gets assigned next (breaking any ties alphabetically).

Which variable gets assigned next?

<ol>

 <li>A</li>

 <li>B</li>

 <li>C</li>

 <li>D</li>

</ol>

<ul>

 <li>The variable you selected should have two values left in its domain. We will use the least-constraining value (LCV) heuristic to decide which value to assign before continuing with the search. To choose which value is the least-constraining value, enforce arc consistency for each value (on a scratch piece of paper). For each value, count the total number of values remaining over all variables.</li>

</ul>

Which value has the largest number of values remaining (and therefore is the least constraining value)?

<ol>

 <li>(1,1) B. (1,2) C. (1,3) D. (2,1) E. (2,2)</li>

 <li>(2,3)</li>

</ol>

<ul>

 <li>After assigning a variable, backtracking search with arc consistency enforces arc consistency before proceeding to the next variable.</li>

</ul>

Write the domains of all variables after assignment of the least-constraining value to the variable you selected and enforcing arc consistency. Note that you already did this computation to determine which value was the LCV.

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1,1)(1,2)B(1,1)C(1,1)(1,2)D(1,1)(1,2)</em></strong>

<ul>

 <li>Is the answer to the previous part a solution to the CSP? Write Yes or No.</li>

</ul>

<h1>Question 2: CSP Properties</h1>

<ul>

 <li>Write all of the following statements about CSPs that are true.

  <ol>

   <li>Even when using arc consistency, backtracking might be needed to solve a CSP.</li>

   <li>Even when using forward checking, backtracking might be needed to solve a CSP.</li>

   <li>None of the above</li>

  </ol></li>

 <li>Select all of the following statements about CSPs that are true.

  <ol>

   <li>When using backtracking search with the same rules to select unassigned variables and to order value assignments (in our case, usually Minimum Remaining Values and Least-Constraining Value, with alphabetical tiebreaking), arc consistency will always give the same solution as forward checking, if the CSP has a solution.</li>

   <li>For a CSP with binary constraints that has no solution, some initial values may still pass arc consistency before any variable is assigned.</li>

   <li>None of the above</li>

  </ol></li>

</ul>




<h1>3: 4-Queens</h1>

The min-conflicts algorithm attempts to solve CSPs iteratively. It starts by assigning some value to each of the variables, ignoring the constraints when doing so. Then, while at least one constraint is violated, it repeats the following: (1) randomly choose a variable that is currently violating a constraint,

(2) assign to it the value in its domain such that after the assignment the total number of constraints violated is minimized (among all possible selections of values in its domain).

In this question, you are asked to execute the min-conflicts algorithm on a simple problem: the 4-queens problem in the figure shown below. Each queen is dedicated to its own column (i.e. we have variables , , , and the domain for each one of them is {A, B, C, D}). In the configuration shown below, we have th th th . Two queens are in conflict if they share the same row, diagonal, or column (though in this setting, they can never share the same column).

You will execute min-conflicts for this problem three times, starting with the state shown in the figure above. When selecting a variable to reassign, min-conflicts chooses a conflicted variable at random. <strong>For this problem, assume that your random number generator always chooses the leftmost conflicted queen. </strong>When moving a queen, move it to the square in its column that leads to the fewest conflicts with other queens. <strong>If there are ties, choose the topmost square among them.</strong>

<em>We recommend you work out the solutions to the following questions on a sheet of scratch paper, and then enter your results below.</em>

<h2>Part 1</h2>

Starting with the queens in the configuration shown in the above figure, which queen will be moved, and where will it be moved to? Write your answer in a form of tuple

(Queen,Position).

<strong><em>Sample Answer: (2,A)</em></strong>

<h2>Part 2</h2>

Continuing off of Part 1, which queen will be moved, and where will it be moved to? Write your answer in a form of tuple (Queen,Position).

<strong><em>Sample Answer: (2,A)</em></strong>

<h2>Part 3</h2>

Continuing off of Part 2, which queen will be moved, and where will it be moved to? Write your answer in a form of tuple (Queen,Position).

<strong><em>Sample Answer: (2,A)</em></strong>

<h1>Tree-Structured CSPs</h1>

There exist efficient solvers for tree-structured CSPs. We can use such solvers in the inner loop of a CSP solver for near-tree-structured CSPs as follows: First find a cutset (i.e. a set of variables such that if removed, the remaining constraint graph forms a tree), then loop over all instantiations of the cutset variables, and for each instantiation call the tree-structured CSP solver to verify if for that instantiation a solution exists; the algorithm terminates when a solution is found or when it has looped over all possible instantiations and no solution was found (and hence the CSP has no solution).

Consider the graph above. Write down the variables that are in the smallest cutset of this graph.

Note: in general, this is a computationally difficult problem. We have not seen an algorithm to compute the minimum cutset in lecture, but for a small graph you should be able to do it by hand (with some effort).

<strong><em>Sample Answer: AB</em></strong>




<h1>Solving Tree-Structured CSPs</h1>

Consider the following tree-structured CSP that encodes a coloring problem in which neighboring nodes cannot have the same color. The domains of each node are shown.

The algorithm for solving tree-structured CSPs starts by picking a root variable. We can pick any variable for this. For this exercise, we will pick . There are several linearizations consistent with as the root; we will use the one shown below.

<h2>Step 1: Remove Backward</h2>

In this step we start with the right-most node ( ), enforce arc-consistency for its parent ( ), then do the same for the second-to-right-most node ( ) and its parent ( ), and so on. Execute this process, and then write the remaining values for all the variables.

<strong><em>Sample Answer:</em></strong>

<strong><em>A(red)B(red,green)C(red,green,blue)D(red)E(red,green)</em></strong>

<h2>Step 2:Assign Forward</h2>

Now that all domains have been pruned, we can find the solution in a single forward pass (i.e. no need for backtracking). This is done by starting at the left-most node ( ), picking any value remaining in its domain, then going to the next variable ( ), picking any value in its domain that is consistent with its parent, and continue left to right, always picking a value consistent with its parent’s assignment.

If at any given node there are multiple colors left that are consistent with its parent’s value, break ties by picking red over green, and then green over blue.

What is the solution found by running the algorithm?

<strong><em>Sample Answer:</em></strong>

<strong><em>A(red)B(green)C(red)D(red)E(green)</em></strong>

<h1>Arc Consistency</h1>

Consider the problem of arranging the schedule for an event. There are three time slots: 1, 2, and 3. There are three presenters: , , and . The variables for the CSP will then be , , and , each with domain {1, 2, 3}. The following constraints need to be satisfied:

<ol>

 <li>,    , and    all need to take on different values</li>

</ol>

2.

<ul>

 <li>Enforce consistency for the arc <strong>A</strong>→<strong>C</strong>, and then write down which values remain for each variable.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1)B(1,2)C(1,2,3)</em></strong>

<ul>

 <li>Starting from the result of the previous step, enforce consistency for the arc <strong>B</strong>→<strong>A</strong>, and then write down which values remain for each variable.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1)B(1,2)C(1,2,3)</em></strong>

<ul>

 <li>Starting from the result of the previous step, enforce consistency for the arc <strong>C</strong>→<strong>A</strong>, and then write down which values remain for each variable.</li>

</ul>

<strong><em>Sample Answer:</em></strong>

<strong><em>A(1)B(1,2)C(1,2,3)</em></strong>

<h1>Arc Consistency Properties</h1>

Assume you are given a CSP and you enforce arc consistency. Which of the following are true?

<ol>

 <li>If the CSP has no solution, it is guaranteed that enforcement of arc consistency resulted in at least one domain being empty.</li>

 <li>If the CSP has a solution, then after enforcing arc consistency, you can directly read off the solution from resulting domains.</li>

 <li>In general, to determine whether the CSP has a solution, enforcing arc consistency alone is not sufficient; backtracking may be required. D. None of the above.</li>

</ol>

<h1>Backtracking Arc Consistency</h1>

We are given a CSP with only binary constraints. Assume we run backtracking search with arc consistency as follows. Initially, when presented with the CSP, one round of arc consistency is enforced. This first round of arc consistency will typically result in variables having pruned domains. Then we start a backtracking search using the pruned domains. In this backtracking search we use filtering through enforcing arc consistency after every assignment in the search. Which of the following are true about this algorithm?

<h2>Part 1</h2>

Which of the following are true about this algorithm?

<ol>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domains of all of the not yet assigned variables being empty, this means the CSP has no solution.</li>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domain of one of the not yet assigned variables being empty, this means the CSP has no solution. C. None of the above. <strong>Part 2</strong></li>

</ol>

Which of the following are true about this algorithm?

<ol>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domains of all of the not yet assigned variables being empty, this means the search should backtrack because this particular branch in the search tree has no solution.</li>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domain of one of the not yet assigned variables being empty, this means the search should backtrack because this particular branch in the search tree has no solution. C. None of the above. <strong>Part 3</strong></li>

</ol>

Which of the following are true about this algorithm?

<ol>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domains of all of the not yet assigned variables each having exactly one value left, this means we have found a solution.</li>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domains of all of the not yet assigned variables each having more than one value left, this means we have found a whole space of solutions and we can just pick any combination of values still left in the domains and that will be a</li>

</ol>




solution.

<ol>

 <li>If after a run of arc consistency during the backtracking search we end up with the filtered domains of all of the not yet assigned variables each having more than one value left, this means we can’t know yet whether there is a solution somewhere further down this branch of the tree, and search has to continue down this branch to determine this.</li>

</ol>
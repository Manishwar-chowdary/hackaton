CONNECT EVERY VILLAGE AT LOWEST COST
1. Introduction

The main problem is to connect every village with roads while keeping the construction cost as low as possible.

When the budget is limited, we need to select only the necessary roads. Mathematics and graph algorithms can help us find the cheapest solution.

The goal is:

Connect all villages using the minimum total road construction cost.

The project uses the Minimum Spanning Tree (MST) concept.

2. Mathematical Model

The road network can be represented as a weighted graph.

Node: Represents a village.
Edge: Represents a possible road between two villages.
Weight: Represents the construction cost of that road.

For example:

A ---- B
 \     |
  \    |
   C---D

Each road has a different construction cost.

The goal is to select a group of roads that connects all villages with the lowest total cost.

3. Network Constraints

A valid road network must satisfy two important rules.

Rule 1: Connected

Every village must be connected to the network.

There should be a path from any village to every other village, possibly through other villages.

Example:

A ---- B ---- C

Here, A can reach C through B.

Rule 2: No unnecessary loops

We should avoid roads that create unnecessary cycles.

Example:

A ---- B
 \    /
  \  /
   C

If A can already reach B through C, another direct road from A to B may be unnecessary.

Removing unnecessary loops helps reduce construction cost.

4. Minimum Spanning Tree

A Minimum Spanning Tree (MST) is a network that:

Connects all villages.
Does not contain unnecessary loops.
Has the minimum possible total construction cost.

For V villages, an MST requires exactly:

V - 1 roads

For example, if there are 6 villages:

6 - 1 = 5 roads

So, 6 villages can be connected using exactly 5 roads in the MST.

5. Example

Suppose there are six villages:

A, B, C, D, E, F

Possible roads and costs are:

Road	Cost
A - B	$2M
B - C	$3M
C - D	$4M
D - E	$5M
B - E	$6M
E - F	$7M
A - F	$8M

We select the cheaper roads while making sure they do not create a loop.

Selected roads
A - B = $2M
B - C = $3M
C - D = $4M
D - E = $5M
E - F = $7M

Total:

2 + 3 + 4 + 5 + 7 = $21M

Therefore:

Minimum construction cost = $21M

The roads B-E ($6M) and A-F ($8M) are rejected because they create unnecessary loops after all villages are already connected.

6. Kruskal's Algorithm

Kruskal's Algorithm is used to find the Minimum Spanning Tree.

It works in three simple steps.

Step 1: Sort roads by cost

Arrange all roads from cheapest to most expensive.

Example:

$2M
$3M
$4M
$5M
$6M
$7M
$8M
Step 2: Check for loops

Take the cheapest road.

If it connects two different groups of villages → select it.
If it creates a loop → reject it.
Step 3: Stop at V - 1 roads

For 6 villages, stop after selecting:

6 - 1 = 5 roads

At this point, all villages are connected with minimum cost.

7. Prim's Algorithm

Another method for finding an MST is Prim's Algorithm.

Prim's algorithm starts from one village and grows the network step by step.

Phase 1

Choose a starting village.

Example:

A
Phase 2

Find the cheapest road from the connected network to an unconnected village.

Phase 3

Continue adding the cheapest suitable road until all villages are connected.

Both Kruskal's Algorithm and Prim's Algorithm can produce the same minimum total cost.

8. Final Conclusion

The main decision rule is:

Connect villages cheaply and never create an unnecessary loop.

The system should:

Calculate the Minimum Spanning Tree.
Use Kruskal's or Prim's algorithm.
Make sure every village is connected.
Reject unnecessary roads that create loops.
Calculate and report the final minimum construction cost.

This approach helps planners make road construction decisions that connect all villages while keeping the total cost as low as mathematically possible.

One-line project explanation

“Our project uses Kruskal's Minimum Spanning Tree algorithm to connect every village with the minimum possible road construction cost while avoiding unnecessary loops.”
Team:4

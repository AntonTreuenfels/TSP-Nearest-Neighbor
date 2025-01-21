This repository contains some experiments regarding approximate solutions to the Traveling Salesman's Problem.

Problem examples are Euclidean 2D ones taken from TSPLIB. They range in size from 51 to 442 nodes, and have known optimal solutions to which results of these experiments can be compared.

The general approach taken here is to construct all Nearest Neighbor tours for a given problem (one for each node) and then try to improve each one. The resulting minimum, maximum and average tours are compared to the known optimal tour. Results are presented both as visual plots and summary statistics.

It is known that an optimal tour never crosses itself. While the initial tours constructed often cross themselves, none of the improved tours do.

The improvement function is perhaps the most unique factor in these experiments. For every pair of nodes, it tries to reverse all the nodes between them (a known approach), but also to move one of the two to other end of the node string and to exchange just the two nodes (all of which seem to be tried more rarely).

The first experiments simply apply whichever change results in the greatest decrease, and so are purely determinisitic. Later experiments note when more than one change results in a reduction and probablistically choose between them.

The minimum length route found is usually within 2% of the optimum (often within 1%, and sometimes exactly the optimum), while the average over all improved routes is usually within 5% of the optimum.

No experiment consistently produced the minimum length tour found, but overall the results are remarkably robust - often differing by less than a tenth of a percent - no matter what approach is tried. However, in general first comparing nodes which are far apart rather than close together yielded slightly better results.

The minimum length route found is usually within 2% of the optimum (often within 1%, and sometimes exactly the optimum), while the average over all improved routes is usually within 5% of the optimum.

The experiments are presened in the form of Jupyter notebooks running Python 3.7. Each file contains the output of what was tried for that experiment, so TSPLIB itself is not required to see the results (though it will be in order to play with any of the experiments).

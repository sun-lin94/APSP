# APSP
CSE591 Project
Sun Lin 108674057
CSE 591 Instructor Liu
2016, Nov. 9

Project Proposal: Calculating All Pair Shortest Path (APSP) in Complex Networks

Your final handin should include a project report, that describes
(1) the problem, i.e., what's given and what's wanted for your project,
(2) the method that you use to solve the problem,
(3) the implementation of the method, and
(4) the results, including the runs and tests you performed, with resulting
numbers, plots, graphs, etc. Each part should also include brief
justifications for why you did what you did.

Description:
(1) I will be focusing on APSP algorithms to find shortest paths between all
nodes in a peer to peer network. The network is a directed graph, where a edge
represents a one way link between two distict nodes. In computer networks,
there are many protocols that is designed to route packets between machines.
However, since the network is generally unknown, and even if it is known, the
scale of the network is so large, we cannot keep the data centralized. This
creates problems, since if a link breaks, the routing must change to find
another feasible path. In some algorithms, this path pathing takes a long time
to converge. The alternate approach is to keep a centralized copy of the
network, and calculate a global routing table. This way, the change in
network topology can be captured, and the routing can be changed to reflect
the change. The problem with this is, trying to find the route is a heavy
computational load for the centralized source. Therefore, we can invest in
time in examining different APSP algorithms that can increase the efficiency
of shortest path calculation.

(2) I plan on implementing the new APSP algorithm proposed by the authors in
the following paper:
https://pdfs.semanticscholar.org/5a78/fb704aa05ce2c9b5afada2543f19f26f3cac.pdf
The first step is to understand the algorithm being proposed, and why the
approach is being used. The method is to compute all path interatively
until the weight converge.
The following is the pseudo-code for the well known Floyd Warshall algorithm:
https://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm
I will also be comparing the mentioned algorithms with Johnson's APSP
algorithm,

(3) The code will be written in either C or C++. The pseudo-code presented in
the previous section will be used for teh actual implementation. The following
is Johnson's algorithm implemented in C++:
https://gist.github.com/ashleyholman/6793360

(4) The analysis consists of 2 parts: clarity and efficiency. The 3 algorithms
will first be compared in terms of clarity. Since they are written in the
same language, we will access the difficulty of understanding the algorithmic
approach.
Then, the 3 algorithms will use the peer to peer directed graph datasets from
https://snap.stanford.edu/data/ to evaluate efficiency. 3 sets of timed values
will be collected from the algorithms, and the graphs will be plotted for
num_node vs time, and num_edge vs time.
The data set does not include any negative links, but the algorithms presented
are capable of calculating APSP even if there are negative links. There should
be no negative cycles in the graph.

# stats-for-networks

## Introduction

Networks are becoming evermore prevalent, from social networks to transport networks, and it is becoming increasingly important to develop practical methods to analyse what can be extremely large datasets of this form.

This repo is a collection of notebooks created whilst taking the Oxford graduate course *Probability and Statistics for Network Analysis* in 2020 (taught by Prof. Gesine Reinert). It covers a few of the topics taught in the course and some from non-statistical network analysis:

- centrality measures
- summary statistics of graphs
- random graph models
- sampling from networks
- fitting a model
- community structures
- motifs

I'd previously worked with deterministic network analysis techniques but these are not practical when dealing with very large networks. Even just visualising the graph - i.e. knowing what your data actually looks like - can become unfeasible, nevermind using algorithms that assume complete knowledge of the network. So, my aim with this course was to develop some practical skills to analyse graphs using statistical techniques.

## Some of the basics

A *network* or *graph* (more commonly used in maths) is a set of vertices/nodes $V$ and edges $E=\{(u,v) | u,v\in V\}$. They can have all sorts of other stucture such as

- vertex weights/labels,
- edge weights/labels,
- directed edges (in this case, the edges $(u,v)$ and $(v,u)$ are different),
- self loops (an edge from a vertex $v$ to itself), 
- multiple edges (i.e. more than one distinct edge between the same two vertices), etc.

For example, a transport network might have vertices representing junctions and edges representing the roads between them. If our aim is to use this network to find the shortest route from $a$ to $b$ then we need to know what distance each edge (road) represents. This is a case where we would use edge weights. If we were interested in the *quickest* route from $a$ to $b$ then we could instead weight the edges by the time taken to traverse each road.

A graph is *simple* if it contains no multiple edges and no self loops.

Graphs are often summarised by their *adjacency matrix $A$*, which has entries $A_{i,j}=1$ if there is an edge from node $v_i$ to node $v_j$ and $A_{i,j}=0$ if there is no such edge. If $n=|V|$ then $A$ is an $n\times n$ matrix. If $G$ is an undirected graph then this matrix is symmetric.

This can be adapted for weighted graphs by replacing any $1$ entry with the edge weight.

Another matrix commonly associated to a graph is the *Laplacian $L$*, defined as $L=D-A$, where $D$ is the diagonal matrix with $D_{i,i}$ as the degree of the vertex $v_i$ and $D_{i,j}=0$ for $i\neq j$, and $A$ is the adjacency matrix.

*The content is loosely based on the lecture notes provided by Prof. Reinert.*

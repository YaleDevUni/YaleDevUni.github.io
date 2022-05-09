---
title:  "Definitions of Graph"
categories: 
  - Algorithms
toc: true
toc_sticky: true
use_math: true
---

## Graph<br /><br />

A graph G = (V,E) consists of
  - a set V of vertices(nodes)
  - a collection E of pairs of vertices(nodes) from V called edges(arcs)

Example of Graph:

![image-left]({{ site.url }}{{ site.baseurl }}/assets/images/graph_sample.png){: .align-left} vertices = V : [a,b,c,d,e]<br /> edges = E : [[a,b],[a,b],[b,c], [b,d], [c,d], [d,e],[e,e]] or [f,g,h,i,j,k,v]
<br /><br /><br /><br />
## Undirected Edges
An undirected edge **h** represents a symmetric relationship between vertices **b** and **c**. In ohter words, edge **h** has both directions between vertices **b** and **c**.<br /><br />
 ![image-right]({{ site.url }}{{ site.baseurl }}/assets/images/graph_sample.png){: .align-right} 
 - We can represent **h = [b,c]**, where **[b,c]** is an unordered pair<br />
 - **b** and **c** are the endpoints of the edge<br />
 - **b** is **adjacent** to **c**<br />
 - **h** is **incident** to **b** and **c**<br />
 - The **degree** of a vertex is the number of incident edges<br />
 &ensp; e.g. **deg(b)** = 4, **deg(e)** = 3
 - **Parallel edges**(multi-edges): more than one edge between pairs of vertices<br />
 - **Self-loop**: edge that connects a vertex to itself(e.g. **e**)<br /><br /><br />

## Undirected Paths

 A **walk** in a graph is a sequence of vertices **$v_1,v_2,v_3,...,v_k$**, such that there exist edges **$[v_1,v_2],[v_2,v_3],...,[v_{k-1},v_k]$**<br />
 - The **length** of a walk is the numver of edges.<br />
 - If $v_1=v_k$, the walk is **closed**. Otherwise, it is **open**.<br /><br />
 - If no edge is repeated, it is a **trail**.<br />
 - A closed trail is is a **circuit**.<br /><br />
 - **Path**: no vertex is repeated.<br />
 - **Cycle**: a path with the same start and ed vertices<br /><br />

## Connected Graphs

**connected graph** : every pair of vertices is connected by a path
 ![image-right]({{ site.url }}{{ site.baseurl }}/assets/images/graph_sample.png){: .align-right}
ex)<br />
- **Connected** graph<br />
 ![image-right]({{ site.url }}{{ site.baseurl }}/assets/images/graph_disconnected.png){: .align-right}
<br /><br /><br /><br />
 - **Disconnected** graph
 - Two **connected components**<br /><br />

## Simple Graphs
A **simple graph** is a graph with **no self-loops and no parallel / multi-edges**<br />
- **Theorem**: $\sum_{v \in V}deg(v)=2m$, where m stands for number of edge, and v stands for a vertex.<br />
- **Theorem**: Let **G** be a simple graph with **n** vertices and **m** edges, Then, $m \le \frac {n(n-1)} {2}$<br />
- **Corollary**: A simple graph with **n** vertices has $O(n^2)$ edges<br /><br />

## Complete Graphs

**Complete graph**: simple graph where every pair of vertices is connected by an edge<br />
- The complete graph on **n** vertices has exactly $\frac{n(n-1)}{2}$ edges <br />
- The complete graph on **n** vertices with one self-loop per vertex has exactly $\frac{n(n+1)}{2}$ edges <br /><br />

## Subgraphs
A **subgraph** of **G = (V,E)** is a graph **G' = (V', E')** where<br />
&ensp; - $V'\subseteq V$<br />
&ensp; - E' consists of edges **[u,v]** in **E** such that both **u** and **v** are in **V'** <br />
A **spanning subgraph** **G'** of **G** contains all vertices of **G**<br />
An **induced subgraph G'** of **G** contains all the edges of **G** that have both endpoints in **G'**<br /><br />

## Trees and Forests
A **(free)tree** is an undirected graph **T** such that<br />
 &ensp; - **T** is connected<br />
 &ensp; - **T** has no cycles<br />
A **rooted tree** is a trees where one vertex is designated as the root<br /><br />
**Forest**: undirected graph without cycles(collection of disconnected trees)
 &ensp; - The connected components of a forest are trees<br /><br />
## Spanning Trees and Forests
A **Spanning Tree** of a connected graph is a spanning subgraph that is a tree<br />
 &ensp; - A spanning tree is not unique unless the graph is tree<br />
A **spanning forest** of a graph is a spanning subgraph that is a forest(e.g. disconnected subgraph that has all vertices) <br /><br />
## Properties of Graphs, Trees, and Forests
**Theorem**: Let **G** be an undirected simple graph with **n** vertices and **m** edges. Then have the following:<br />
- If G is connected, then $m \ge {n-1}$ <br />
- If G is a tree, then $m=n-1$ <br />
- If G is a forest, then $m \le n-1$ <br />
---
title: "An Introduction to Graph Theory"
date: 2021-09-18T23:44:03+07:00
draft: false
categories: [Discrete Math]
tags: [graph-theory]
author: Curious Duck
featuredImage: "feature-image.jpeg"
summary: ""
math: true
---

## What is Graph Theory?

### The Seven Bridges of Königsberg

#### Problem Description

This history of graph theory is considered to be started from 1973 with a paper by _Leonhard Euler_. In his paper, Euler has introduced an elegant way to solve the _Seven Bridges of Königsberg_ - one the most well-known problem in mathematics.

The problem set theme in the city of Königsberg in Prussia (now Kaliningrad, Russia). The Pregel River divided the city into 2 mainlands and 2 large islands, whom are connected by seven bridges.

<center> {{<image src="TKBP-1.jpeg" caption="The Seven Bridges of Königsberg">}} </center>

The question is simple: **Can you draw a path to walk through the city (i.e cross all the seven bridges) without crossing each bridge more than once?**  

If you haven't known this problem or its solution, I suggest you not to look at the below answer right away. Instead, let spend five minutes to try to solve it on your own first, then look at the answer. I will put a picture of a duck here as a break.

<center> {{<image src="duck.png" caption="Confusing duck">}} </center>

#### Euler's Solution

Now, let's see how Euler used _graph theory_ to solve the problem.

<center> {{<image src="TKBP-1.jpeg">}} </center>
<center> {{<image src="TKBP-2.png" caption="Graph representation of the problem">}} </center>

Euler reformulated the problem into _vertices_ and _edges_:
- Each _vertex_ (point) represents a piece of land
- Each _edge_ (line) represents a bridge.

So we will have a graph representation of the original problem in figure b with 4 vertices, connected to each other by a total of 7 edges.

To be able to cross all the briges without crossing each more than once, the number of edges connected to a vertex need to be an _even_ number (except for the ones chosen for start and finish), because once we enter a piece of land, we need another bridge to walk away from it. In this problem, we can see that all 4 vertices are touched by an an _odd_ number of edges (3 or 5). Since we can only have one starting point and one finishing point, there can be only 2 vertices that have an _odd_ number of adjacent edges. This leads to a contradiction; hence, it is impossible to solve the problem.


### The Four Knights Puzzle

#### Problem Description

I will give one more demonstration of using graph theory to solve another interesting problem, called the _Four knights puzzle_

<center> {{<image src="4knights.jpeg" caption="The Four Knights Puzzle (source: https://www.geeksforgeeks.org)">}} </center>

The puzzle is again, simple: **Given a 3x3 chess table with 4 knights, 2 blacks and 2 whites, standing at four corners of the table as shown in the left figure. How many steps does it take to have a result in the right figure**

If you are interested in solving this, I will not spoil the answer immediately. Instead, you will have another 5 minutes to try solving it on your own. Here come the duck again

<center> {{<image src="duck.png" caption="Confusing duck, again">}} </center>

#### Solution

As we have seen in the first problem, to model the problem using graph theory, we will transform it into vertices and edges:
- Each vertex represents a square. We will label them from 1 to 9 as in the following matrix:
<center>$\begin{bmatrix} 1B & 2 & 3B \\\ 4 & 5 & 6 \\\ 7W & 8 & 9W \end{bmatrix}$</center>

- Each edge represents the possibility to move from one square to another. For you who don't know how to play chess, a knight has an _L-shaped_ move. For example, the knight at square 1 can move to either square 6 or 8.

<center> {{<image src="4knights-graph.png" caption="Graph representation of the Puzzle (source: https://www.geeksforgeeks.org)">}} </center>

The above graph illustrates the initial and desired state of the game. As we can see, to solve this problem, we need to be able to reorder the knights from Black-Black-White-White to Black-White-Black-White. This is impossible because the order will always remain the same no matter what moves we make except when a knight can leap over another.


### Graph Theory Definition and Applications

So far, you might have a sense of what graphs are. By definition, **Graphs are discrete structures consisting of vertices and edges that connect these vertices.** Problems in almost every conceivable discipline can be solved using graph model. In the above puzzles, you can make many trials trying to solve the games. After a while, you might feel that the problem is unsolvable, but you don't have a solid method to actually prove it. That's when Graph Theory comes into play.

Graphs can be used to model many types of relations and processes in a variety of areas, from physics, biology to information systems, and has a wide range of applications such as:
- <a href="https://www.researchgate.net/publication/225582780_Food_webs_competition_graphs_and_the_boxicity_of_ecological_phase_space">Representing the competition of different species in an ecological niche</a>
- <a href="https://www.pnas.org/content/101/9/2658">Finding communities in networks, such as social media</a>
- <a href="https://www.researchgate.net/publication/220208413_Graph_theory_application_and_web_page_ranking_for_website_link_structure_improvement">Web page ranking</a>
- <a href="https://en.wikipedia.org/wiki/Shortest_path_problem#:~:text=In%20graph%20theory%2C%20the%20shortest,its%20constituent%20edges%20is%20minimized">Finding the shortest path between two points in a transportation network (Route Optimization)</a>
- etc

## Fundamental Concepts of Graph Theory

Now let's go through some basic concepts in Graph Theory

### Graph

> A graph $G = (V, E)$ consists of $V$, a nonempty set of vertices (or nodes) and $E$, a set of edges. Each edge has either one or two vertices associated with it, called its endpoints. An edge is said to connect its endpoints.

Graphs can be classified into:
- **Simple graphs** or **multigraphs** depending on the number of edges between two vertices

<center> {{<image src="graph2.png" caption="**Simple graph** - no more than one edge connected the same pairs of vertices">}} </center>
<center> {{<image src="graph3.png" caption="**Multigraph** - may have multiple edges connecting the same vertices">}} </center>

- **Undirected graphs** or **directed graphs (or digraphs)** depending on the direction of the edges
<center> {{<image src="graph3.png" caption="**Undirected graph** - edges have no direction">}} </center>
<center> {{<image src="graph4.png" caption="**Directed graph** - edges have directions">}} </center>


### Adjacency Matrix and Incidence Matrix

> Two vertices $u$ and $v$ in an undirected graph G are called *adjacent* (or neighbors) in $G$ if $u$ and $v$ are endpoints of an edge $e$ of $G$.
Such an edge $e$ is called *incident* with the vertices $u$ and $v$ and $e$ is said to connect $u$ and $v$.

Let consider the following multiple undirected pseudograph
<center> {{<image src="graph5.png" caption="A pseudograph">}} </center>

- We can represents this graph by an _incidence matrix_, with 5 rows represents 5 vertices: $v_1,v_2, .., v_5$, and 8 columns represents 8 edges $e_1, e_2, .., e_8$. The value is 1 if the edge is incident with the vertex, and 0 otherwise
$$\begin{bmatrix} 1&1&1&0&0&0&0&0 \\\ 0&1&1&1&0&1&1&0 \\\ 0&0&0&1&1&0&0&0 \\\ 0&0&0&0&0&0&1&1 \\\ 0&0&0&0&1&1&0&0 \end{bmatrix}$$

- Or we can also represents the graph by an _adjacency matrix_, with rows and columns represent 5 vertices $v_1, v_2, ..., v_5$ in the same order. Each value is the number of edges that connects two corresponding vertices
$$\begin{bmatrix} 1&2&0&0&0 \\\ 2&0&1&1&1 \\\ 0&1&0&0&1 \\\ 0&1&0&1&0 \\\ 0&1&1&0&1 \end{bmatrix}$$


### Degree of a vertex

- Degree in undirected graphs:

> The degree of a vertex in an undirected graph is the number of edges incident with it, except that a loop at a vertex contributes twice to the degree of that vertex.
The degree of the vertex $v$ is denoted by $deg(v)$.


- Degree in directed graphs:

> In a directed graph:
> - The in-degree of a vertex $v$, denoted by $deg^{-}(v)$, is the number of edges with $v$ as their terminal vertex, i.e $v$ is the end of these edges
> - The out-degree of $v$, denoted by $deg^{+}(v)$, is the number of edges with $v$ as their initial vertex, i.e $v$ is the start of these edges
(Note that a loop at a vertex contributes 1 to both the in-degree and the out-degree of this vertex.)


- Total degree:
> Let G = (V, E) be a graph with m edges. Then $$2m = \sum_{v \in  V} deg(v)$$
> We can see that the total degree in a graph is always an even number


### Isomorphism of Graphs

> The simple graphs $G_1 = (V_1, E_1)$ and $G_2 = (V_2, E_2)$ are *isomorphic* if there exists a one-to-one
> and onto function $f$ from $V_1$ to $V_2$ with the property that $a$ and $b$ are adjacent in $G_1$ if
> and only if $f(a)$ and $f(b)$ are adjacent in $G_2$, for all $a$ and $b$ in $V_1$. Such a function $f$ is called an isomorphism.
> Two simple graphs that are not isomorphic are called *nonisomorphic*.  
>
> In other words, when two simple graphs are isomorphic,
> there is a one-to-one correspondence between vertices of the two graphs that preserves the adjacency relationship.

{{<image src="graph6.png" caption="Two isomorphic graphs">}}

In the above example, we have 2 graphs: $G = (V, E)$ and $H = (W, F)$. If we map $G$ to $H$ by function $f$ with
$f(u_1) = v_1, f(u_2) = v_4, f(u_3) = v_3, f(u_4) = v_2$, the adjacency is preserved. Therefore, two graphs $G$ and $H$ are isomorphic


## More Resources

In this article, I have covered some fundamental concepts in Graph Theory, and demonstrated a few examples of using Graph Theory to solve real problems.
To have a deeper understanding, learn more concepts and applications of Graph Theory, there are some good resources for you:
- *Discrete mathematics and its applications, Kenneth H. Rosen* (Most of the content in this article is referred from this book)
- *Graph Theory, by Bondy and Murty* (Book in *Graduate Texts in Mathematics* - a series of graduate-level textbooks in mathematics published by Springer-Verlag)
- *Digraphs - Theory, Algorithms and Applications, by Gregory Gutin and Jørgen Bang-Jensen*

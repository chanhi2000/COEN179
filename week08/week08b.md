# week08b

## PRIM's ALGORITHM

## KRUSKAL's ALGORITHM
- find the shortest edge to add without completing a cycle.
- add it to subgraph
- repeat these following process.

## IMPLEMENTATION
- to find the shortest edges, sort the edges by weights.
- if we suppose $$E$$ to be the \# of edges, then
$$
f(n)=O(\left|E\right|\:\log{\left|E\right|})
$$

WITH EVERY NEW EDGE
- if it connects to unseen vertices, start a new component.
- if it connects a known vertex to an unseen vertex, add the unseen vertex to the old component (along with the edge), and mark the vertex seen.
- if it connects two known vertices decide if they'are in the same component.

- if yes, skip it
- if no, add the edge and fuse the component

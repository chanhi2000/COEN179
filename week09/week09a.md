# week09a

## KRUSKAL'S ALGORITHM (Finding minimum spaning tree)

1. set the edges by weights.
2. for each edge 
	- if it connects unseen vertices, create anew component.
	- if it connects an old vertex to a new vertex, add the edge to the component of the old vertex
	- if it connects two seen vertices of same componenets, discard it
	- if it connects two seen vertices, of different components, use the edge to combine two components into one.

- last one may cost a lot.

## UNION-FIND DATA STRUCTURE.
- **find**: "find the caption of the team"
- **union**: "group"
- implement "reversed tree".


## UNION-FIND: PSEUDOCODE 
`Find(n)`
- if `parent(n)==n`, `return n`
- otherwise 
	- set `parent(n)=parent(parent(n))`
	- return `find(parent(n))`

`Union(m,n)` 
- if `Find(m)`≠`Find(n)`, set 
	- `parent(find(m))=find(n)`, or
	- `parent(find(n))=find(m)`, or
	- chosose descendant on "*rank*"
		- if ranks equal, the add to the rank





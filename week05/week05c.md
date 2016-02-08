# week05c

## RED-BLACK TREES (implement 2-3-4 trees)

#### rules
- red: internal comparison
- black: external comparison
- **internal**: if im inside of 3 or 4.
- **external**: otherwise.

$$
d1 | d2 | d3\\
z, z, z, z
$$

$$
d2\\
d1\:\:\:\:d3
$$
- top of the tree (parent node) is always black.
- no red child of red parents
- black depth of the tree remains constant down any path from top to bottom.
- any new node starts as a leaf of the tree, wherever it fits.


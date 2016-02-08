# week05b

## RANDOMLY GENERATED TREE

#### EX#1: RANDOM (wack)
$$
R
$$
$$
\:\:\:\:\:\:\:\:R\\
A\\
$$
$$
\:\:\:\:\:\:\:\:R\\
A\\
\:\:\:\:\:\:\:\:N\\
$$
$$
\:\:\:\:\:\:\:\:R\\
A\\
\:\:\:\:\:\:\:\:N\\
D\\
$$
$$
\:\:\:\:\:\:\:\:R\\
A\\
\:\:\:\:\:\:\:\:N\\
\:\:\:\:\:\:\:\:D\:\:\:\:\:\:\:\:O\\
$$
$$
\:\:\:\:\:\:\:\:R\\
A\\
\:\:\:\:\:\:\:\:N\\
\:\:\:\:\:\:\:\:D\:\:\:\:\:\:O\\
\:\:\:\:M\\
$$
- **problem**: the tree didn't spread out evenly


## BINARY TREE
RANDOM->ADMNOR.
$$
\:\:\:\:\:\:\:\:M\\
\:\:\:\:\:\:A\:\:\:\:\:\:O\\
\:\:\:\:\:\:\:\:\:\:\:\:D\:\:N\:\:R
$$


## 2-3 NODE TREE
- 2-node: 1 comparison
- 3-node: 2 comparisons two different ways.
- 2-3 node: witht the same depth on every path to the bottom.

#### EX#1: RANDOM
**R**:
$$
R\\
$$
**A**: are you single or dobule? Let me be your roommate.
$$
A\:\:|\:\:R\\
$$
**N**: we don't have any room for you, N. go up
$$
N\\
A\:\:\:\:R\\
$$
**D**: i have to know my place. I'll room with you, A.
$$
N\\
A|D\:\:\:\:R\\
$$
**O**: i have to know my place. I'll room with you D.
$$
N\\
A|D\:\:\:\:O|R\\
$$
**M**: i have to know my place. I'll room with you guys.
$$
N\\
A|D|M\:\:\:\:O|R\\
$$
D, you can't stay with us. move up.
$$
D|N\\
A|M\:\:\:\:O|R\\
$$
let's change up a little
$$
D|N\\
A\:\:\:\:\:M\:\:\:\:\:O|R\\
$$


## what about 4-node / 2-comparisons?
 - i think it's as efficient as 3 node structure.
 - well that's just binary tree.


##red black
- # of black links is the same on any pth from top to the botoom.
- no two reds in c row.


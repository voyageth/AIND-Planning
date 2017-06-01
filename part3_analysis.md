# Analysis

## Provide an optimal plan for Problems 1, 2, and 3.
### Problem 1
```
Load(C1, P1, SFO)
Fly(P1, SFO, JFK)
Load(C2, P2, JFK)
Fly(P2, JFK, SFO)
Unload(C1, P1, JFK)
Unload(C2, P2, SFO)
```

### Problem 2
```
Load(C1, P1, SFO)
Fly(P1, SFO, JFK)
Load(C2, P2, JFK)
Fly(P2, JFK, SFO)
Load(C3, P3, ATL)
Fly(P3, ATL, SFO)
Unload(C3, P3, SFO)
Unload(C2, P2, SFO)
Unload(C1, P1, JFK)
```

### Problem 3
```
Load(C2, P2, JFK)
Fly(P2, JFK, ORD)
Load(C4, P2, ORD)
Fly(P2, ORD, SFO)
Load(C1, P1, SFO)
Fly(P1, SFO, ATL)
Load(C3, P1, ATL)
Fly(P1, ATL, JFK)
Unload(C4, P2, SFO)
Unload(C3, P1, JFK)
Unload(C2, P2, SFO)
Unload(C1, P1, JFK)
```


## Compare and contrast non-heuristic search result metrics (optimality, time elapsed, number of node expansions) for Problems 1,2, and 3. Include breadth-first, depth-first, and at least one other uninformed non-heuristic search in your comparison; Your third choice of non-heuristic search may be skipped for Problem 3 if it takes longer than 10 minutes to run, but a note in this case should be included.
### Problem 1
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 1.breadth-first   | 43    | 56    | 180   | 6     | 0.05485508700076025   |
| 3.depth-first     | 21    | 22    | 84    | 12    | 0.026748197997221723  |
| 5.uninformed-cost | 55    | 57    | 224   | 6     | 0.06200596899725497  |


### Problem 2
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 1.breadth-first   | 3343    | 4609    | 30509   | 9     | 13.73563324099814   |
| 3.depth-first     | 624    | 625    | 5602    | 619    | 3.4453577819949714  |
| 5.uninformed-cost | 4852    | 4854    | 44030   | 9     | 12.536586457994417  |

### Problem 3
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 1.breadth-first   | 14663    | 18098    | 129631   | 12     | 104.7384856580029   |
| 3.depth-first     | 408    | 409    | 3364    | 392    | 1.8231443029944785  |
| 5.uninformed-cost | 18235    | 18237    | 159716   | 12     | 55.453882379006245  |



## Compare and contrast heuristic search result metrics using A* with the "ignore preconditions" and "level-sum" heuristics for Problems 1, 2, and 3.
### Problem 1
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 8. astar_search h_1   | 55    | 57    | 224   | 6     | 0.063888392993249   |
| 9. astar_search h_ignore_preconditions     | 41    | 43    | 170    | 6    | 0.06453962798696011  |
| 10. astar_search h_pg_levelsum | 11    | 13    | 50   | 6     | 0.5583404400094878  |

### Problem 2
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 8. astar_search h_1   | 4852    | 4854    | 44030   | 9     | 12.879883941001026   |
| 9. astar_search h_ignore_preconditions     | 1450    | 1452    | 13303    | 9    | 4.93801516800886  |
| 10. astar_search h_pg_levelsum | 86    | 88    | 841   | 9     | 45.054660214984324  |

### Problem 3
| Search |  Expansions | Goal Tests | New Nodes | Plan length | Time elapsed | 
| --- | --- | --- | --- | --- | --- |
| 8. astar_search h_1   | 18235    | 18237    | 159716   | 12     | 54.506712503003655   |
| 9. astar_search h_ignore_preconditions     | 5040    | 5042    | 44944    | 12    | 17.71721396999783  |
| 10. astar_search h_pg_levelsum | 325    | 327    | 3002   | 12     | 234.63691881799605  |



## What was the best heuristic used in these problems? Was it better than non-heuristic search planning methods for all problems? Why or why not?
- if need optimal solution : exclude depth-first.
  - if Time elapsed is most important : choose a* with h_ignore_preconditions.
  - if spatial efficiency is most important : choose a* with h_pg_levelsum.

- if optimal is not important and Time elapsed & spatial efficiency is most important : depth-first.


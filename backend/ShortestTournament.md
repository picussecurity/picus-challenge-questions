# Shortest Tournament

Members of a Go club are arranging a tournament. The list of players
who will play against each other will be determined by the
council. This list will have a pair of member IDs on each line. Each
match will take exactly 30 minutes. There are an infinite number of
tables in the tournament place and the order the list is written is
irrelevant.

Sample input:

```
1 2
2 3
3 4
4 5
1 5
```

The problem you need to solve is finding the game plan which will take
the shortest time.

For example, considering the sample input; if games [(1,2), (3,4)] are
played between minutes 0-30, games [(2,3), (4,5)] are played between
minutes 30-60 and the game [(1,5)] is played between minutes 60-90;
the tournament will be finished in 90 minutes.

Sample output (list of list of tuples):

```
[[(1, 2), (3, 4)], [(2, 3), (4, 5)], [(1, 5)]]
```

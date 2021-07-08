# concepts-notes

# List Comprehension
You can generate lists using list comprehension 

```haskell
[x |x <- [1..5]]

[1,2,3,4,5]
```
You can manipulate generated lists 

```haskell
[x ^ 2|x <- [1..5]]

[1,4,9,16,25]
```
You can operate on multiple lists
```haskell
[(x,y) |x <- [1..4], y <- [1..3]]

[(1,1),(1,2),(1,3),(2,1),(2,2),(2,3),(3,1),(3,2),(3,3),(4,1),(4,2),(4,3)]
```

One can also add a guard or a condition that must be fulfilled
```haskell
[(x,y) |x <- [1..4], y <- [1..3],x /= y]

[(1,2),(1,3),(2,1),(2,3),(3,1),(3,2),(4,1),(4,2),(4,3)]
```

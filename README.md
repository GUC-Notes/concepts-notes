# concepts-notes

# Haskell 
## List Comprehension
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
## Some Data Structures in Haskell
Defining a Binary Tree
```haskell
data BTree a = Null | TreeNode a (BTree a) (BTree a) deriving (Show, Eq)
```
Simple Functions of a Binary Tree
```haskell 
root (TreeNode x _ _) = x --returns the root
left (TreeNode _ l _) = l --returns left node
right (TreeNode _ _ r) = r --returns right node

isEmpty Null = True
isEmpty _ = False

size Null = 0
size (TreeNode _ l r) = 1 + (size l) + (size r)

preOrder Null = []
preOrder (TreeNode x l r) = x : ((preOrder l) ++ (preOrder r)) --generates the preorder traversal of a tree

fromListPre [] = Null
fromListPre (x:xs) = TreeNode x l r      --generates a Binary Tree from a given preorder traversal 
    where
        mid = div (length xs) 2
        l = fromListPre (take mid xs)
        r = fromListPre (drop mid xs)
``` 
Defining a LinkedList
```haskell
data LinkedList a = Node a (LinkedList a) | Null deriving (Show, Eq)
```
Simple Functions of a LinkedList
```haskell
hd (Node x _) = x  --returns the head of the list

tl (Node _ t) = t  --returns the tail of the list

fromList [] = Null
fromList (x:xs) = Node x (fromList xs)  --generating a linkedlist from a given normal list

toList Null = []
toList (Node a t) = a : (toList t)  --converting a linked list to a normal list

addHead x y = Node x y  --adds to the head of the list 

addTail x Null = Node x Null
addTail x (Node a t) = Node a (addTail x t)   --adds to the tail of the list

mx (Node x Null) = x
mx (Node x t) = if x > y then x else y   --returns the maximum value in the list
    where y = mx t
```

-----------------------------------------------------
# C



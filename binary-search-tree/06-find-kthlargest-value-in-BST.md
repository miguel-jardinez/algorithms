# Min Height BST

Write a function that takes in a Binary Search Tree (BST) and a positive integer ```k``` 
and returns the kth largest integer contained in the BST.

You can assume that there will only be integer values in the BST and that ```k``` 
is less than or equal to the number of nodes in the tree.

Also, for the purpose of this question, duplicate integers will be treated as distinct values. 
In other words, the second largest value in a BST containing values ```{5, 7, 7}``` will be ```7```—not ```5```.

Each ```BST``` node has an integer ```value```, a left child node, and a right child node.
A node is said to be a valid ```BST``` node if and only if it satisfies the ```BST``` property:
its ```value``` is strictly greater than the values of every node to its left; its ```value``` is
less than or equal to the values of every node to its right; and its children nodes are
either valid BST nodes themselves or ```None``` / ```null```.


## Sample input

```code
tree =   15
       /     \
      5      20
    /   \   /   \
   2     5 17   22
 /   \         
1     3       
k = 3
```

## Sample output

```code
17
```


## Hints

### Hint 1
Make sure to consider the fact that the given tree is a Binary Search 
Tree—not just a regular Binary Tree. How does this fact help 
you solve the problem in a more optimal time complexity?

### Hint 2
The brute-force approach to this problem is to simply perform an 
in-order traversal of this BST and to store all of its node' 
values in the order in which they're visited. 
Since an in-order traversal of a BST visits the nodes in ascending order, 
the kth value from the end of the traversal order will be the kth largest value.

### Hint 3
You can actually solve this problem in O(h + k) time, where 
h is the height of the tree. Rather than looking at the nodes in 
ascending order, you should look at them in descending order.

### Hint 4
To solve this problem in O(h + k) time as mentioned in Hint #3, 
you need to perform a reverse in-order traversal. 
Since you'll be looking at nodes in descending order, 
you can simply return the kth visited node in the reverse in-order traversal.

### Optimal Space & Time Complexity
O(h + k) time | O(h) space - where h is the height of the tree and k is the input parameter

# Testing scenarios
### Test Case 1

```code
{
  "tree": {
    "nodes": [
      {"id": "15", "left": "5", "right": "20", "value": 15},
      {"id": "20", "left": "17", "right": "22", "value": 20},
      {"id": "22", "left": null, "right": null, "value": 22},
      {"id": "17", "left": null, "right": null, "value": 17},
      {"id": "5", "left": "2", "right": "5-2", "value": 5},
      {"id": "5-2", "left": null, "right": null, "value": 5},
      {"id": "2", "left": "1", "right": "3", "value": 2},
      {"id": "3", "left": null, "right": null, "value": 3},
      {"id": "1", "left": null, "right": null, "value": 1}
    ],
    "root": "15"
  },
  "k": 3
}
```

### Test Case 2

```code
{
  "tree": {
    "nodes": [
      {"id": "5", "left": "4", "right": "6", "value": 5},
      {"id": "4", "left": "3", "right": null, "value": 4},
      {"id": "6", "left": null, "right": "7", "value": 6},
      {"id": "7", "left": null, "right": null, "value": 7},
      {"id": "3", "left": null, "right": null, "value": 3}
    ],
    "root": "5"
  },
  "k": 1
}
```

### Test Case 3

```code
{
  "tree": {
    "nodes": [
      {"id": "5", "left": null, "right": null, "value": 5}
    ],
    "root": "5"
  },
  "k": 1
}
```

### Test Case 4

```code
{
  "tree": {
    "nodes": [
      {"id": "20", "left": "15", "right": "25", "value": 20},
      {"id": "15", "left": "10", "right": "19", "value": 15},
      {"id": "25", "left": "21", "right": "30", "value": 25},
      {"id": "10", "left": null, "right": null, "value": 10},
      {"id": "19", "left": null, "right": null, "value": 19},
      {"id": "21", "left": null, "right": "22", "value": 21},
      {"id": "30", "left": null, "right": null, "value": 30},
      {"id": "22", "left": null, "right": null, "value": 22}
    ],
    "root": "20"
  },
  "k": 3
}
```

### Test Case 5

```code
{
  "tree": {
    "nodes": [
      {"id": "1", "left": null, "right": "2", "value": 1},
      {"id": "2", "left": null, "right": "3", "value": 2},
      {"id": "3", "left": null, "right": "4", "value": 3},
      {"id": "4", "left": null, "right": "5", "value": 4},
      {"id": "5", "left": null, "right": null, "value": 5}
    ],
    "root": "1"
  },
  "k": 5
}
```

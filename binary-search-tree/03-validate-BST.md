# Validate BST

Write a function that takes in a potentially invalid Binary Search Tree (BST) and returns a boolean representing whether the BST is valid.

Each ```BST``` node has an integer ```value```, a left child node, and a right child node. 
A node is said to be a valid ```BST``` node if and only if it satisfies the ```BST``` property: 
its ```value``` is strictly greater than the values of every node to its left; its ```value``` is 
less than or equal to the values of every node to its right; and its children nodes are 
either valid BST nodes themselves or ```None``` / ```null```.

A BST is valid if and only if all of its nodes are valid ```BST``` nodes.


## Sample input

```code
tree =   10
       /     \
      5      15
    /   \   /   \
   2     5 13   22
 /           \
1            14
```

## Sample output

```code
true
```


## Hints

### Hint 1
Every node in the BST has a maximum possible value and a minimum possible value. In other words, the value of any given node in the BST must be strictly smaller than some value (the value of its closest right parent) and must be greater than or equal to some other value (the value of its closest left parent).

### Hint 2
Validate the BST by recursively calling the validateBst function on every node, passing in the correct maximum and minimum possible values to each. Initialize those values to be -Infinity and +Infinity.

### Optimal Space & Time Complexity

O(n) time | O(d) space - where n is the number of nodes in the BST and d is the depth (height) of the BST

# Testing scenarios
### Test Case 1

```code
{
  "tree": {
    "nodes": [
      {"id": "10", "left": "5", "right": "15", "value": 10},
      {"id": "15", "left": "13", "right": "22", "value": 15},
      {"id": "22", "left": null, "right": null, "value": 22},
      {"id": "13", "left": null, "right": "14", "value": 13},
      {"id": "14", "left": null, "right": null, "value": 14},
      {"id": "5", "left": "2", "right": "5-2", "value": 5},
      {"id": "5-2", "left": null, "right": null, "value": 5},
      {"id": "2", "left": "1", "right": null, "value": 2},
      {"id": "1", "left": null, "right": null, "value": 1}
    ],
    "root": "10"
  }
}
```

### Test Case 2

```code
{
  "tree": {
    "nodes": [
      {"id": "10", "left": "5", "right": "15", "value": 10},
      {"id": "15", "left": null, "right": "22", "value": 15},
      {"id": "22", "left": null, "right": null, "value": 22},
      {"id": "5", "left": "2", "right": "5-2", "value": 5},
      {"id": "5-2", "left": null, "right": null, "value": 5},
      {"id": "2", "left": "1", "right": null, "value": 2},
      {"id": "1", "left": "-5", "right": null, "value": 1},
      {"id": "-5", "left": "-15", "right": "-5-2", "value": -5},
      {"id": "-5-2", "left": null, "right": "-2", "value": -5},
      {"id": "-2", "left": null, "right": "-1", "value": -2},
      {"id": "-1", "left": null, "right": null, "value": -1},
      {"id": "-15", "left": "-22", "right": null, "value": -15},
      {"id": "-22", "left": null, "right": null, "value": -22}
    ],
    "root": "10"
  }
}
```

### Test Case 3

```code
{
  "tree": {
    "nodes": [
      {"id": "10", "left": null, "right": null, "value": 10}
    ],
    "root": "10"
  }
}
```

### Test Case 4

```code
{
  "tree": {
    "nodes": [
      {"id": "10", "left": "5", "right": "15", "value": 10},
      {"id": "15", "left": null, "right": "22", "value": 15},
      {"id": "22", "left": null, "right": "500", "value": 22},
      {"id": "500", "left": "50", "right": "1500", "value": 500},
      {"id": "1500", "left": null, "right": "10000", "value": 1500},
      {"id": "10000", "left": "2200", "right": null, "value": 10000},
      {"id": "2200", "left": null, "right": null, "value": 2200},
      {"id": "50", "left": null, "right": "200", "value": 50},
      {"id": "200", "left": null, "right": null, "value": 200},
      {"id": "5", "left": "2", "right": "5-2", "value": 5},
      {"id": "5-2", "left": null, "right": null, "value": 5},
      {"id": "2", "left": "1", "right": null, "value": 2},
      {"id": "1", "left": null, "right": null, "value": 1}
    ],
    "root": "10"
  }
}
```

### Test Case 5

```code
{
  "tree": {
    "nodes": [
      {"id": "5000", "left": "5", "right": "55000", "value": 5000},
      {"id": "55000", "left": null, "right": null, "value": 55000},
      {"id": "5", "left": "2", "right": "15", "value": 5},
      {"id": "15", "left": "5-2", "right": "22", "value": 15},
      {"id": "22", "left": null, "right": "502", "value": 22},
      {"id": "502", "left": "204", "right": null, "value": 502},
      {"id": "204", "left": "203", "right": "205", "value": 204},
      {"id": "205", "left": null, "right": "207", "value": 205},
      {"id": "207", "left": "206", "right": "208", "value": 207},
      {"id": "208", "left": null, "right": null, "value": 208},
      {"id": "206", "left": null, "right": null, "value": 206},
      {"id": "203", "left": null, "right": null, "value": 203},
      {"id": "5-2", "left": null, "right": null, "value": 5},
      {"id": "2", "left": "1", "right": "3", "value": 2},
      {"id": "3", "left": null, "right": null, "value": 3},
      {"id": "1", "left": null, "right": "1-2", "value": 1},
      {"id": "1-2", "left": null, "right": "1-3", "value": 1},
      {"id": "1-3", "left": null, "right": "1-4", "value": 1},
      {"id": "1-4", "left": null, "right": "1-5", "value": 1},
      {"id": "1-5", "left": null, "right": null, "value": 1}
    ],
    "root": "5000"
  }
}
```
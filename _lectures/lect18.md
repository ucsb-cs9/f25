---
num: "Lecture 18"
desc: "Binary Search Trees cont."
ready: true
lecture_date: 2025-12-02 11:00:00.00-7:00
---

Recorded Lecture: [12_2_25](https://drive.google.com/file/d/1xGN_VwF5xP2r-wl8XghDNOoWqeJRvPDD/view?usp=drive_link)

# BST Deletion

* We can break up deletion in three cases:
    * **Case 1:** When the node to be deleted is a leaf node (no children)
    * **Case 2:** When the node to be deleted has one child
    * **Case 3:** When the node to be deleted has two children

## Case 1: Delete a leaf node
* Find the node that needs to be deleted
* Simply remove the parent reference (either left child or right child) to the deleted node

![BSTDeleteCase1.png](BSTDeleteCase1.png)

## Case 2: Delete a node with one child
* Connect the deleted Node’s parent and the deleted Node’s child together

![BSTDeleteCase2.png](BSTDeleteCase2.png)

## Case 3: Delete a node with two children
* First find the successor (node with next greater value) in the right subtree
    * This can be done by traversing the left children of the node to be deleted’s right subtree
    * Also note that the successor will always only have **at most** one child
        * If the successor had a left child, then it wouldn’t be the successor!
* Temporarily store the successor and delete the successor from the tree
    * Deleting the successor will fall in either Case 1 or Case 2
* Replace the deleted node’s value with the successor’s value

![BSTDeleteCase3.png](BSTDeleteCase3.png)

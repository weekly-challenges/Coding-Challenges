
```
Challenge: 128

Write a binary search function that has the functionality of:

insert(int val): void
lookup(int val): boolean 
remove(int val): void

#coding #challange #easy
```

Solution Attempt #1: (In Java)

```java
package org.example;

public class BinarySearchTree {

  public BinaryNode root;

  public static void main(String[] args) {
    BinarySearchTree binarySearchTree = new BinarySearchTree();
    binarySearchTree.insert(8);
    binarySearchTree.insert(3);
    binarySearchTree.insert(10);
    binarySearchTree.insert(1);
    binarySearchTree.insert(6);
    binarySearchTree.insert(4);
    binarySearchTree.insert(7);
    binarySearchTree.insert(14);
    binarySearchTree.insert(13);
    binarySearchTree.print(binarySearchTree.root);
    System.out.println("14 found :" + binarySearchTree.lookup(14));
    System.out.println("-10 found :" + binarySearchTree.lookup(-10));
    binarySearchTree.remove(1);
    System.out.println("1 found :" + binarySearchTree.lookup(1));
    binarySearchTree.remove(14);
    System.out.println("14 found :" + binarySearchTree.lookup(14));
    binarySearchTree.print(binarySearchTree.root);
    binarySearchTree.remove(3);
    System.out.println("3 found :" + binarySearchTree.lookup(3));
    binarySearchTree.print(binarySearchTree.root);
  }

  public BinarySearchTree() {
    this.root = null;
  }

  public void insert(int val) {
    BinaryNode newNode = new BinaryNode();
    newNode.val = val;

    if (this.root == null) {
      this.root = newNode;

    } else {
      BinaryNode temp = this.root;
      while (true) {
        if (temp.val > val) {
          if (temp.left == null) {
            temp.left = newNode;
            break;
          } else {
            temp = temp.left;
          }
        } else {
          if (temp.right == null) {
            temp.right = newNode;
            break;
          } else {
            temp = temp.right;
          }
        }
      }
    }
  }

  public boolean lookup(int val) {
    BinaryNode node = this.root;
    if (node != null && node.val == val) {
      return true;
    }

    while (node != null && node.val != val) {
      if (node.val > val) {
        node = node.left;
      } else {
        node = node.right;
      }
    }

    return node != null;
  }

  public void remove(int val) {
    boolean isFound = lookup(val);
    if (!isFound) {
      throw new RuntimeException("Value not found");
    }
    BinaryNode nodeToRemove = this.root;
    BinaryNode parentNode = null;
    while (nodeToRemove != null) {
      System.out.println("Node val in " + nodeToRemove.val);
      if (nodeToRemove.val == val) {
        if (nodeToRemove.left == null && nodeToRemove.right == null) {
          System.out.println("No sub child");
          if (parentNode != null && parentNode.right.val == val) {
            parentNode.right = null;
          }
          if (parentNode != null && parentNode.left.val == val) {
            parentNode.left = null;
          }
          break;
        } else if (nodeToRemove.left == null) {
          System.out.println("Node to left is empty");
          if (parentNode != null) {
            if(parentNode.left != null && parentNode.left.val == val){
              parentNode.left = nodeToRemove.right;
            }
            if(parentNode.right != null && parentNode.right.val == val){
              parentNode.right = nodeToRemove.right;
            }
          }
          break;
        } else if (nodeToRemove.right == null) {
          System.out.println("Node to right is empty");
          if (parentNode != null) {
            if(parentNode.left != null && parentNode.left.val == val){
              parentNode.left = nodeToRemove.left;
            }
            if(parentNode.right != null && parentNode.right.val == val){
              parentNode.right = nodeToRemove.left;
            }
          }
          break;
        }
      }

      parentNode = nodeToRemove;

      if (nodeToRemove.val > val) {
        System.out.println("Node val in " + nodeToRemove.val);
        nodeToRemove = nodeToRemove.left;
      } else {
        System.out.println("Node val in " + nodeToRemove.val);
        nodeToRemove = nodeToRemove.right;
      }
    }
  }

  public void print(BinaryNode binaryNode) {
    if (binaryNode == null) {
      return;
    }
    System.out.println("                Node " + binaryNode.val);
    System.out.print("Left " + (binaryNode.left != null ? binaryNode.left.val : "null"));
    System.out.println(
        "                                 right " + (binaryNode.right != null ? binaryNode.right.val
            : "null"));
    print(binaryNode.left);
    print(binaryNode.right);
  }

  public static class BinaryNode {

    public int val;
    public BinaryNode left;
    public BinaryNode right;
  }
}
```

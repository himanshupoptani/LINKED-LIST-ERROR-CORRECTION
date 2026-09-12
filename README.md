# LINKED-LIST-ERROR-CORRECTION
## Changes Made

I made some small changes in the delete functions so that the program works properly in different cases.

### Changes in delete from end

In the old code, deleting the last node was working for a normal list, but it could give an error when there was only one node or when the list was empty.

So I added a check for these cases. If the list is empty, nothing is deleted. If there is only one node, that node is deleted and the head is made `NULL`.

I also changed the function so that it returns the updated head.

### Changes in delete from start

I added a check for an empty list before deleting the first node. This prevents the program from trying to access a node when there is no node in the list.

After deleting the first node, the head is moved to the next node.

### Change in memory deletion

I changed `free()` to `delete` because the nodes are created using `new`. This is the proper way to delete the nodes in C++.

### Change in main function

While calling `deleteNodeAtEnd()`, I stored the returned value back in `head`.

```cpp
head = deleteNodeAtEnd(head);
```

This is needed because after deleting the last node, the head can change, especially when there was only one node.

Overall, these changes make the delete operations work correctly for empty, single-node, and multiple-node linked lists.


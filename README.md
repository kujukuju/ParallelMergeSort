
## Parallel Merge Sort

Simple parallel merge sort that tries to avoid using locks as much as possible.

Has the best performance out of the couple of different parallel sort alternatives I've tested.

When initialized it will create the next equal or highest power of 2 thread count as you have logical cores. This is so that the logic of the work splitting up the tree can remove 1 thread from work every move.

This removes the need for locks as you can just atomic count up to 2 the number of finished children since you now have a perfect tree.

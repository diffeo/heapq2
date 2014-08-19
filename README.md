heapq2
======

Python standard library list.sort() takes an comparison function argument, so heapq should too.

These functions have been extended to take a cmp_lt(a,b) function which returns True if a is less than b:

   * heappush(), heappop(), heapreplace(), heappushpop(), heapify(), nlargest(), nsmallest(), merge()

The default cmp_lt functions as before, using a.__lt__(b) if available, or falling back to (b >= a).

An 'index=0' argument has been added to heappop() and heapreplace() so that an element other than the head of the heap-queue can be popped.

Other guidance on the Python standard library heapq routines suggested wrapping objects in a tuple with the sort key in the first element and the value in the second, or using a wrapper object that defined __lt__(), but in maintaining a queue of many millions of elements the object overhead gets problematic and replacing all those wrapper objects with one comparison function is efficient.
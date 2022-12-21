---
banner: "![[Banner-1.png]]"
banner_y: 0.36667
---

# Asymptotic Analysis: Big-O Notation and More

The efficiency of an algorithm depends on the amount of time, storage and other resources required to execute the algorithm. The efficiency is measured with the help of notations.

An algorithm may not have the same performance for different types of inputs. With the increase in the input size, the performance will change.

The study of change in performance of the algorithm with the change in the order of the input size is defined as asymptotic analysis.

## #asymptotic-notations

asymptotic notations are mathermatical notations used to describe the runing time of an algorithm when the input tends towards a particular value or a limiting value.

F.e: In bubble sort, when the input array is already sorted, the time taken by the algorithm is linear i.e the best case.

But, when the input array is in reverse condition, the algorithm takes the maximum time to sort the elements i.e the worst case.

When the input array is neither sorted nor in reverse order, then it takes average time. These durations are denoted using asymptotic notations.

There are mainly three asymptotic notations:

-   Big-O notation
-   Omega notation
-   Theta notation
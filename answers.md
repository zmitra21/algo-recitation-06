# CMPS 2200 Recitation 06
## Answers

**Name:** Zack Mitra



Place all written answers from `recitation-06.md` here for easier grading.



- **1)** Before we implement a heap, let's consider if we just maintain
 an unordered list/sequence. 

  - **1a) (1 pt)** What is the work/span of *deleteMin*?
  For an unordered list, deleteMin requires scanning all (n) elements to identify the minimum. Since the scan is sequential, both the work and span are (O(n)).
  - **1b) (1 pt)** What is the work/span ofand *insert(x)*?
  insert(x) simply appends the element to the end of the list. Therefore, both the work and span are (O(1)) amortized.
- **2a) (1 pt)** For a heap with $n$ elements, what does this imply about the depth of the associated almost-complete binary tree? 
Since an almost-complete binary tree fills each level before adding another, the number of nodes approximately doubles with each additional level. Therefore, a heap with n elements has a depth of log(n), which is Theta(log(n)).
- **2b) (1 pt)** By maintaining the heap property, where is the minimum element of
  the heap? Can we say anything about the maximum element?
  The minimum element is always located at the root of the min-heap because every parent is less than or equal to its children. The maximum element must be located at one of the leaf nodes, but we cannot determine exactly which leaf without searching.
- **4a) (1 pt)** What is the work/span of *reheapUp*($x$)?
    reheapUp: The work and span are both O(log(n)) because the heap has a logarithmic height, and in the worst case, an element must move from the bottom to the root. Each swap takes constant time, and the swaps must happen sequentially
- **4b) (1 pt)** What is the work/span of *reheapDown*($x$)? 
    reheapDown: The work and span are both O(log(n)) because an element may need to move from the root to a leaf in the worst case. Each comparison and swap takes constant time, and the swaps happen sequentially.
- **6) (1 pt)** What is the work and span of `heapsort`?
    The work and span of heapsort are both O(nlog(n)). We first insert n elements into the heap, with each insertion taking O(log(n)) time in the worst case. We then perform n deleteMin operations, each also taking O(log(n)) time. Since these operations are performed sequentially, the total work and span are both O(nlog(n))
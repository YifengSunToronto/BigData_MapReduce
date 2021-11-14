# BigData_MapReduce
MapReduce is good 'Divide and Conquor' solution for Big-Data Batch Processing

When should we use MapReduce?
Problems that can be solved by MapReduce must lend themselves to parallelization, i.e., the various parts can be solved independently to produce intermediate results that are later merged to arrive at a final solution.

It is :
Distributed - Distributed Map and Reduce nodes  
Parallel: accpet input in-parallel and each batch of data is processed independently
Fault-Tolerant - can re-schedule failed
Scalable: More resource = more process ability


There are 2 main procedes: 1. Map and 2.Reduce
![image](https://user-images.githubusercontent.com/32372822/141699322-8a419021-3e24-4aa6-9891-8019608c44d4.png)

1. Input: Batches of data that can be processed offline and in-parallel
2. Map: Need a map function -> map key-val pair to generate a set of intermidiate key-val paris. This is like chop the input data to small pecies so it can be shuffled and merged.
3. Shuffle: For each output of Map node, re-orgnize them such that the same key paris are grouped together
4. Reduce: Merge output of Shuffle, which is the orgnized intermidiate key-valu paris, to put the same key pairs together.
5. Output: Key-val pairs

# BigData_MapReduce
MapReduce is good 'Divide and Conquer' solution for Big-Data Batch Processing

When should we use MapReduce?
Problems that can be solved by MapReduce must lend themselves to parallelization, i.e., the various parts can be solved independently to produce intermediate results that are later merged to arrive at a final solution.

It is :
Distributed - Distributed Map and Reduce nodes can work together to Chop the input data and Merge them back
Parallel: accpet input in-parallel and each portion of input data is processed independently
Fault-Tolerant - can re-schedule failed
Scalable: More resource = more process ability


Work with HDFS - HDFS has good performance for frequent write

![image](https://user-images.githubusercontent.com/32372822/141702107-213d9abc-1b29-4ef5-9fe5-12ee88d07833.png)

There are 2 main procedes: 1. Map and 2.Reduce
![image](https://user-images.githubusercontent.com/32372822/141699322-8a419021-3e24-4aa6-9891-8019608c44d4.png)
![image](https://user-images.githubusercontent.com/32372822/141702719-fbd452f6-c1aa-4e8f-b046-2a99fb34455b.png)

1. Input: Batches of data that can be processed offline and in-parallel
2. Map: Need a map function -> map key-val pair to generate a set of intermidiate key-val paris. 
3. This is like chopping the input data to small pecies so it can be shuffled and merged.
4. Each Map node is working on a data split independently.
5. Shuffle: For each output of Map node, re-orgnize(Sort by Key) them such that the same key paris are closed to each others. Then move the output to Reducers based on Reducers partition policy.
6. Reduce: Merge output of Shuffle, which is the orgnized intermidiate key-valu paris, to put the same key pairs together.
7. Each Reduce node is working on a range of key-value pairs independently.
8. Output: Key-val pairs


![image](https://user-images.githubusercontent.com/32372822/141702903-430d10e2-9e75-4be8-a66b-810bca7a07c1.png)


Classic Demostration
- WordCount / ObjectFrequencyCount

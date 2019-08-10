
## [Hybrid computing using a neural network with dynamic external memory](https://www.nature.com/articles/nature20101)

### (Alexander Graves et.al)


### General Summary

+ Paper is an extension of NTM architecture

+ External memory block is used to surpass short term memory issue in deep neural networks

+ Three different attention mechanisms are defined for reading/writing/replacing in external memory

### Background

+ Proposed method of using external differentiable memory block is inspired from human memory theory mainly focusing on attribute theory, similarity measures, search of associative memory, temporal context model and serial recall

+ Proposed soft attention mechanisms, content-lookup for reading from the memory block, attention of temporal links for replacing memory and attention for writing in memory matrix

+ Method is an end to end differentiable extension of Neural Turing Machine

### Method

+ Entire architecture is divided into 4 blocks, controller (neural network), read-write heads, memory block, and temporal weightage block

+ Controller Block: mapping function

+ Read-Write Block: variable weight vectors which encodes the position in memory block where to write or read from memory

+ Memory Block: Differentiable block which stores past signals, which will be used for further learning

+ Temporal Block: Differentiable weight block which encodes the similarity between rows of memory block

+ The output of the controller is not only governed by input but also on one/many feature vectors in memory block


### Results

+ The experiments were conducted on graph problems on family trees and london underground, along with copying task
 
+ The results outperforms pre-existing LSTM, NTM techniques

+ The experiments on reinforcement learning shows the promising results in extending the research direction


### Advantages and Future Directions

+ The method provides strong direction for memory augmented methods which can be used for multi-domain association problems

+ They hold the state information for a long amount of time, providing sufficient time for self correction

+ Some ideas for multi-agent, multi-domain adaptations can be drawn from this paper

+ If interested in exploring any of the above ideas, message me: koriavinash1@gmail.com


### References

+ https://www.nature.com/articles/nature20101

+ https://deepmind.com/blog/article/differentiable-neural-computers

+ https://greydanus.github.io/2017/02/27/differentiable-memory-and-the-brain/

+ https://github.com/deepmind/dnc


```python

```

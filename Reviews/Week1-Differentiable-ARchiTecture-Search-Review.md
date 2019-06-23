
## [DARTS: Differentiable Architecture Search](https://arxiv.org/pdf/1806.09055.pdf)

### General Summary

+ Differentiable approach for meta learning with pre-specified search space

+ Authors proposed gradient based method for neural architecture search, which makes the entire process to be differentiable.

+ At each step network gets chance to choose between k network building block, by weighing each block separately. These variables are optimized using gradient descent

+ Final set of block are obtained based on the highest weighing parameter among all k


### Background

+ Neuroevolution with an augmented topology (NEAT), Hyper NEAT, NASNet, AutoML are few methods involving genetic algorithm, reinforcement learning techniques for neural architecture search. Check references if you are interested in any of the aforementioned methods

+ Major work in this paper is inspired by the work of Blender et.al from their work of Understanding and Simplifying One-Shot Architecture Search, where the main idea of weight sharing was introduced

+ The results seems to outperform other state-of-the-art algorithms like, Learning transferable architecture for scalable image recognition and Acceleration of stochastic approximation by averaging, in-terms of scalability and accuracy on CIFAR and ImageNet


### Approach and Methods

+ Bilevel optimization problem is formulated, one for optimizing alphas and other for weight optimization

+ The search space is formulated using limited operations like: convolution with defined kernel size, downsampling, upsampling operations

+ Weights and networks are initialized randomly and continuous relaxation problem is solved by mixing candidate operations proposed in the search space

+ Joint optimization of weights and alphas is done by iteratively solving bilevel optimization of loss which is the function of weights and network architecture

+ Final network is selected based on the max softmax outputs over all the optimized alphas


### Results

+ Training time was reduced from 3000 GPU days to 4 GPU days

+ Number of parameters in an optimal networks remains close to previously proposed state-of-the-art methods

+ Proposed methods outperforms various other methods based on evolutionary and reinforcement learning in terms of test error and accuracy in the tasks of image classification (CIFAR-10 and ImageNet), language modelling (PTB) 



### Conclusions

+ Proposed method is easily scalable to any tasks or any datasets

+ DARTS can be considered as an optimal and fast way for architectural search


### Other information

+ As the proposed methods makes use of predefined set of operations for building the network, it ideally doesn't results to the best possible network. This kind of approach results in dis-continious search topology which helps for faster convergence

+ The source code is also open source  and can be accessed at: [https://github.com/quark0/darts](https://github.com/quark0/darts)

+ Overall very interesting approach for architecture search


### References

+ DARTS: [https://arxiv.org/pdf/1806.09055.pdf](https://arxiv.org/pdf/1806.09055.pdf)

+ AutoML: [https://www.automl.org/automl/literature-on-neural-architecture-search/](https://www.automl.org/automl/literature-on-neural-architecture-search/)




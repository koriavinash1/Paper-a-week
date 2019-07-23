
## [The 1000 Brain Theory of Intelligance](https://www.frontiersin.org/articles/10.3389/fncir.2018.00121/full)

### (Jeff Hawkins, Marcus Lewis, Mirko Klukas, Scott Purdy and Subutai Ahmad)


### General Summary

+ Authors proposed a method describing how brain might possibly work in perceiving the external environment

+ Authors make a claim that entire neocortex region of the brain is full or grid cells like neurons

+ Rather than learning one model brain tries to formulates 1000's of models and make decisions based on deductive reasoning

+ Our brain is not a single brain it behaviors as if 1000's of brain working simultaneously


### Background

+ Neocortex is the region in the cerebral cortex, which is related to perception and auditory signals

+ Grid cells are group of neurons whose simultaneous firing signifies tries to model two-dimensional external environment. Grid cells plays a major role in perceiving 3D space around us and also plays an important role in navigation

+ Recent studies based in fMRI analysis shows that neocortex is formed by the group of grid cells

+ In this paper the authors propose grid cell based technique to learn structure of objects and external environment


### Method

+ According to many theories causality and long-standing view in neocortex is the main reason for making decisions, but thousand brains theory is very different from them

+ According to thousand brain theory, the brain creates 1000s of models of an environment and decides based on deductive reasoning. Based on sensory signals are combined with the grid cell derived location, and long reange cortical connections work together and quickly identify objects

+ Authors have provided an example of coffee cup in the paper, which demonstrates the entire effect of the proposed theory


### AI takeaways

+ All the existing loss functions (in deep learning) optimizes variables for feature selection, but optimization for feature deduction might open up new possibilities, if it's actually followed in brain

+ If we convert this problem to credit assignment problem, this proposed model can be formulated as multiagent reinforcement learning problem. Building a multi-agent framework where each and every agent is trained on different sensory feedback by collecting the experiences in one single buffer and have some attention mechanism to correlate and learn from experiences (something similar to DNC) and taking final decisions based on reward of each network would somewhat simulate the situation


### References

+ https://www.frontiersin.org/articles/10.3389/fncir.2018.00121/full

+ https://numenta.com/blog/2019/01/16/the-thousand-brains-theory-of-intelligence/

## [Truncated Gaussian-Mixture Variational AutoEncoder](https://arxiv.org/pdf/1902.03717.pdf)

### (Qingyu Zhao, Nicolas Honnorat, Ehsan Adeli, Kilian M. Pohl)


### General Summary

+ Authors proposed a semi-supervised method for outlier detection and clustering

+ Proposed method results in infinite minor cluster formation, no need to fix the number of clusters

+ Since GMM's are not feasible for high dimensional or non linear data, methods like VAE's are used to learn the latent embeddings of the data

+ For joint optimization of clustering and outlier detection, the proposed method involves truncated Gaussian-Mixture model embedded in a Variational AutoEncoder framework (tGM-VAE)

+ The main problem addressed in the paper is to cluster out the major clusters (often hindered by minor cluster and heavy noise) in case of rest-state fMRI images


### Background


+ VAE's are powerful models used in generating lower dimensional latent space embeddings of higher dimensional data the encoder tries to approximate the distribution of the latent representation and the aim of the decoder is to reconstruct the similar images

+ There are lots of work in the area of bayesian nonparametric models for modelling infinite number of clusters in unsupervised and semi-supervised way

+ This paper uses the idea of using generative models (multiple VAE's) to capture major states using non-informative prior distribution (which means fixing on the prior data independent prior, in this case Dirichlet's prior)

+ Check references for literature on GMM's, VAE's and AE's and their effect on clustering


### Theory, Approach and Methods

+ Joint optimization for clustering and anomaly detection is formulated, using Gaussian-VAE by maximizing variational lower bound

+ Graphical models for both tGaussian-VAE and reformulated version are discussed in the paper

+ Encoders-Decoders architecture considered for MNIST task just has 3 layers (fully connected), MSE reconstruction loss was considered and SGVB trick was applied for reparameterization

+ In case of exp. three random classes in MNIST was considered as main classes and the rest of them were merged in single minor cluster, selected 3 classes covered 90% of the training data and 10% data points were sampled from remaining 7 classes

+ In case of rs-fMRI study 15k correlation matrices were considered for clustering (obtained from 593 adolescents NCANDA dataset)


### Results

+ For MNIST overall 4 class accuracy obtained was around 88% and for selected 3 class it was around 92.54%

+ Method results in good reconstructed images along with distinct cluster patterns

+ Clustering patterns formed in case of fMRI study shows multiple significant clusters, resulting in close relation with ground truth signal

+ Results indicate that connectivity state tends to persist longer in older adolescents


### Conclusions

+ The proposed strategy is helpful for clustering and anomaly detection at the same time, with single optimization


### Other information

+ Paper is hard to interpret, in many derivations notations are not clearly specified

+ It doesn't come with code for experimenting


### References

+ https://arxiv.org/pdf/1902.03717.pdf

+ https://www.youtube.com/watch?v=ZZGTuAkF-Hw

+ http://anotherdatum.com/vae.html

+ https://arxiv.org/pdf/1312.6114.pdf



## [Poincaré Embeddings for Learning Hierarchical Representations](https://arxiv.org/pdf/1705.08039.pdf)
### (Maximilian Nickel,  Douwe Kiela)


### General Summary

+ Authors propose new non-euclidean project for data embedding

+ A new approach for learning hierarchical representations of symbolic data is proposed, to be more precise technique in the paper describes the projection on latent hirtatchical data on to n dimensional poincare ball (hyperbolic projection)

+ Proposed technique makes use of Riemannian optimization method to learn embeddings, expiremental results in the paper shows that, hyperbolic poincare embeddings outperforms euclidean embeddings with a huge margin


### Background

+ Paper uses the concepts of text embeddings, Riemannian manifold, Minkowski Space and few other topological aspects. Please check refference section if you want to dig deep into these fields

+ Hyperbolic space is selected to explot the structural propoert in the data for learning more abstract and effective representation (It's unclear how paper makes this claim, but qualitative results show proves that statement to an extent)

+ Hyperbolic space can be considered as a continuous version of trees, which means the data with latent hierarchical structures. In this paper authors propose specific type of hyperbolic structure which is poincare ball model, reason being it is well suited for gradient based optimixation and allows for better scalability and development of better optimization algorithms


### Theory, Approach and Methods

+ In case of hyperbolic space, due to its negative curvature, the distance from the point increases expnentially when compared to Euclidean distance, which is helpful in pushing non similar features apart to a greater extent.

+ In case of hyperbolic geometry the tree structure can be easily modeled in two dimensions, tree level is directly propotional to the radius of the n dimensional sphere

+ Authors consider poincare ball for their hyperbolic projection, due to its differentiabilty and the possibility of gradient based optimization

+ Poincare embeddings of text reflects semantic similarities hidden in the data. It also helps in modelling the hierarchy in the embedding space, which is not captured in euclidean space

+ The norm of a point in poincare ball represents its hierarchy and distance between the points represents similarity

+ As a result of this properties, Poincare embeddings helps in learning parsimonious features with better generalization property by reducing runtime and memory complexity. It also helps us in gaining insights of hirearchical realtions from the data

+ RSGD (Remanian SGD) is used in optimization of weights. It turns out that remanian gradients is just the rescaled version of Euclidean gradients, where scaling factor is proportional to inverse of the poincare ball metric tensor. This makes it fully differentiable and easily scalable for larger datasets and deeper networks

+ At each and every iteration the features obtained needs to be projected back to some hyperbolic space (poincare ball in case of paper)

+ For the tasks of embedding taxonomies, network embeddings and lexical entilement, expirements were performed by initializing the embeddings from the uniform distribution from (-0.001, 0.001)


### Results

+ Mean average precision was used for evaluation in case reconstruction and link prediction tasks and spearman’s coefficient was considered in case of lexical entailment

+ In all the reported experiments poincare embeddings outperformed the all the previously existing techniques

+ This proposed method also helped in decreasing number of weight parameters in network without loss in performance


### Conclusions

+ Proposed method learns to capture similarity and hierarchy

+ Better scalability and generalizability of the method is established (only for data with hierarchical structure)


### Other information

+ Paper definately provides out of the box idea for text embeddings, which can be extended to any sort of sequential data

+ The source code is also open source  and can be accessed at: [https://github.com/facebookresearch/poincare-embeddings](https://github.com/facebookresearch/poincare-embeddings)


```python

```

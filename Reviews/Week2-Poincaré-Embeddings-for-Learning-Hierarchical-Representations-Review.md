## [Poincaré Embeddings for Learning Hierarchical Representations](https://arxiv.org/pdf/1705.08039.pdf)
### (Maximilian Nickel,  Douwe Kiela)


### General Summary

+ Authors propose new non-euclidean project for data embedding

+ A new approach for learning hierarchical representations of symbolic data is proposed, to be more precise technique in the paper describes the projection on latent hierarchical data on to n dimensional poincare ball (hyperbolic projection)

+ Proposed technique makes use of Riemannian optimization method to learn embeddings, experimental results in the paper shows that, hyperbolic poincare embeddings outperforms euclidean embeddings with a huge margin


### Background

+ Paper uses the concepts of text embeddings, Riemannian manifold, Minkowski Space and few other topological aspects. Please check reference section if you want to dig deep into these fields

+ Hyperbolic space is selected to exploit the structural properties in the data for learning more abstract and effective representation (It's unclear how paper makes this claim, but qualitative results show proves that statement to an extent)

+ Hyperbolic space can be considered as a continuous version of trees, which means the data with latent hierarchical structures. In this paper authors propose specific type of hyperbolic structure which is poincare ball model, reason being it is well suited for gradient based optimization and allows for better scalability and development of better optimization algorithms


### Theory, Approach and Methods

+ In case of hyperbolic space, due to its negative curvature, the distance from the point increases exponentially when compared to Euclidean distance, which is helpful in pushing non similar features apart to a greater extent.

+ In case of hyperbolic geometry the tree structure can be easily modeled in two dimensions, tree level is directly proportional to the radius of the n dimensional sphere

+ Authors consider poincare ball for their hyperbolic projection, due to its differentiability and the possibility of gradient based optimization

+ Poincare embeddings of text reflects semantic similarities hidden in the data. It also helps in modelling the hierarchy in the embedding space, which is not captured in euclidean space

+ The norm of a point in poincare ball represents its hierarchy and distance between the points represents similarity

+ As a result of this property, Poincare embeddings helps in learning parsimonious features with better generalization property by reducing runtime and memory complexity. It also helps us in gaining insights of hierarchical relations from the data

+ RSGD (Remanian SGD) is used in optimization of weights. It turns out that riemannian gradients is just the rescaled version of Euclidean gradients, where scaling factor is proportional to the inverse of the poincare ball metric tensor. This makes it fully differentiable and easily scalable for larger datasets and deeper networks

+ At each and every iteration the features obtained needs to be projected back to some hyperbolic space (poincare ball in case of paper)

+ For the tasks of embedding taxonomies, network embeddings and lexical entitlement, experiments were performed by initializing the embeddings from the uniform distribution from (-0.001, 0.001)


### Results

+ Mean average precision was used for evaluation in case reconstruction and link prediction tasks and spearman’s coefficient was considered in case of lexical entailment

+ In all the reported experiments poincare embeddings outperformed all the previously existing techniques

+ This proposed method also helped in decreasing number of weight parameters in network without loss in performance


### Conclusions

+ Proposed method learns to capture similarity and hierarchy

+ Better scalability and generalizability of the method is established (only for data with hierarchical structure)


### Other information

+ Paper definitely provides out of the box idea for text embeddings, which can be extended to any sort of sequential data

+ The source code is also open source  and can be accessed at: [https://github.com/facebookresearch/poincare-embeddings](https://github.com/facebookresearch/poincare-embeddings)

### References

+ http://bjlkeng.github.io/posts/hyperbolic-geometry-and-poincare-embeddings/

+ https://arxiv.org/pdf/1705.08039.pdf

+ https://en.wikipedia.org/wiki/Poincar%C3%A9_disk_model

+ https://en.wikipedia.org/wiki/Riemannian_manifold


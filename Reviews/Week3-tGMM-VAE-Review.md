## [Truncated Gaussian-Mixture Variational AutoEncoder](https://arxiv.org/pdf/1902.03717.pdf)

### (Qingyu Zhao, Nicolas Honnorat, Ehsan Adeli, Kilian M. Pohl)


### General Summary

+ Authors proposed a semi-supervised method for outlier detection and clustering

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


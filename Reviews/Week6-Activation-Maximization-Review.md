---
layout: post
title: "Activation Maximization"
date: 2019-08-25
desc: ""
keywords: "AI, Machine_Learning, Optimization"
categories: [AI]
tags: [Technology, Mathematics, Optimization, ML]
icon: icon-centos
---
## Activation Maximization

#### Wanted to try something different, listing new ideas and it's implications 

### Background

+ The variables that these deep neural networks learn to maximize activations at any intermediate layers need not be compared with the human learning process, they may or may not be similar. 

+ It's studied that deep neural networks are biased towards [textural information](https://openreview.net/forum?id=Bygh9j09KX) rather than shapes, which is not the case in humans where our brains try to correlate features based on [shapes and textures.](https://oxfordre.com/neuroscience/view/10.1093/acrefore/9780190264086.001.0001/acrefore-9780190264086-e-75)

+ Holistic view of activation maximization is to find out an input which maximizes specific feature map.

### Methodology

+ Once the network is trained, all the weights are frozen and the variable image is used as an input for the network.

+ To maximize the activation of the specific feature map, the input image is tuned with the gradient-based approach with some additional regularizers. These regularizations helps in preserving the bounds, variance, and style of the generated input image.

+ Addition of each regularization can be easily observed by constraining the maximization function.

### Results 

+ The activation maps obtained from this method preserves the textural information, proving the claim that deep neural networks are biased towards the textural information in the data.

+ The results provide an [evidence](https://distill.pub/2017/feature-visualization/) learning furry patterns, face like texture and many more for the network trained on imagenet.


### Advantages and my experiments

+ For a few of our experiments we have explored the visualization for the networks trained on brain tumor segmentation data. 

+ The activation maps encode the textural information in huge detail, this can be the direction to find the evidence of pathological textures in tumors region.

+ If interested in exploring any of the above ideas, message me: koriavinash1@gmail.com




### References

+ https://openreview.net/forum?id=Bygh9j09KX

+ https://oxfordre.com/neuroscience/view/10.1093/acrefore/9780190264086.001.0001/acrefore-9780190264086-e-75

+ https://distill.pub/2017/feature-visualization/


```python

```

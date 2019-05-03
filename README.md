# fun with optimizers
this is a collection of popular optimizers, implemented with tensorflow.

optimizers are one facet of deep neural networks.  when it comes to training, other considerations include initializations, the choice of activation functions, etc..

## what makes an optimizer a "good" optimizer?
a good gradient descent algorithm should handle the following:
* sparse gradients. there are often regions on the cost surface that are flat and wide. it's easy for an optimizer to get lost on these plateaus, as gradients are small and close to zero.
* noisy objectives. when dealing with stochastic objective functions, gradients are often noisy and could even potentially conflict with each other. 
* small memory footprints. deep learning architectures have millions of parameters. (resnet50, a common backbone, has roughly 25 million parameters.) 
* annealing. step sizes learning rates should decrease as the optimizer approaches a minimum.
* invariance to gradient magnitudes. for deep networks without batch norm.

## implemented optimizers
### stochastic gradient descent
### adam
adam, as described in the 2015 paper ["adam: a method for stochastic optimization"](https://arxiv.org/abs/1412.6980), is one of the most popular optimizers for non convex optimization.

it computes (1) the moving average of the gradient's first moment `m`, and (2) the moving average of the gradient's second moment (grad ^ 2, or the element-wise multiplication of the gradient) `v`. after adjusting for bias (since both moving averages are initialized with zeros), the fraction `m / sqrt(v)` (informally interpreted as a signal to noise ratio) is computed and used to rescale the learning rate.

### momentum
### rmsprop
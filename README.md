# fun with optimizers
this repo is a collection of popular optimizers, cleanly implemented with tensorflow.

optimizers are just one facet of deep neural networks. (other considerations include initializations, activation functions, batch norm, and pretraining.)

## what makes an optimizer a "good" optimizer?
a good gradient descent algorithm should handle the following:
[1] sparse gradients. there are often regions on the cost surface that are flat and wide. it's easy for an optimizer to get lost on these plateaus, as gradients are small and close to zero.
[2] noisy objectives. when dealing with stochastic objective functions, gradients are often noisy and could even potentially conflict with each other. 
[3] small memory footprints. deep learning architectures have millions of parameters. (resnet50, a common backbone, has roughly 25 million parameters.) 
[4] annealing. step sizes learning rates should decrease as the optimizer approaches a minimum.
[5] invariance to gradient magnitudes. for deep networks without batch norm.

## optimizers
### adam
adam, as described in the 2015 paper ["adam: a method for stochastic optimization"](https://arxiv.org/abs/1412.6980), is one of the most popular optimizers for non convex optimization.

it computes (1) the moving average of the gradient's first moment `m`, and (2) the moving average of the gradient's second moment (grad ^ 2, or the element-wise multiplication of the gradient) `v`. after adjusting for bias (since both moving averages are initialized with zeros), the fraction `m / sqrt(v)` (informally interpreted as a signal to noise ratio) is computed and used to rescale the learning rate.

### momentum
TO BE ADDED
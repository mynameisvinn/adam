# fun with optimizers
this repo is a collection of popular optimizers, cleanly implemented with tensorflow.

optimizers are just one facet of deep neural networks. (other considerations include initializations, activation functions, batch norm, and pretraining.)

## adam
adam, as described in the 2015 paper ["adam: a method for stochastic optimization"](https://arxiv.org/abs/1412.6980), is one of the most popular optimizers for non convex optimization.

it computes (1) the moving average of the gradient's first moment `m`, and (2) the moving average of the gradient's second moment (grad ^ 2, or the element-wise multiplication of the gradient) `v`. after adjusting for bias (since both moving averages are initialized with zeros), the fraction `m / sqrt(v)` (informally interpreted as a signal to noise ratio) is computed and used to rescale the learning rate.

## momentum
TO BE ADDED
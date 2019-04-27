# adam
adam is an adaptive learning rate optimization algorithm. it is one of the most popular optimizers for non convex optimization.

## what is this?
a bare bones tensorflow implementation of adam, as described in the 2015 paper ["adam: a method for stochastic optimization"](https://arxiv.org/abs/1412.6980)

## how does it *adaptively* scale learning rates?
adam computes (1) the moving average of the gradient's first moment `m`, and (2) the moving average of the gradient's second moment (grad ^ 2, or the element-wise multiplication of the gradient) `v`.

after adjusting for bias (since both moving averages are initialized with zeros), the fraction `m / sqrt(v)` is computed and used to rescale the learning rate.

as mentioned in the paper, when the gradient information is "noisy", `m` will shrink faster than `v`. as result, `m / sqrt(v)` approaches zero, which can be interpreted as a low signal-to-noise ratio.
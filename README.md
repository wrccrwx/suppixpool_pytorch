# SuperPixelPool-pytorch
superpixel average pooling, superspixel max pooling, pytorch implementations

## compile solution: 
https://github.com/princeton-vl/CornerNet/issues/33

###  solution:
  change the invoking order for at::zeros (in bottom_pool.cpp, left_pool.cpp, right_pool.cpp, top_pool.cpp ) in CornerNet/models/py_utils/_cpools/src,
  
  For example:
  ```
  change: auto max_val = at::zeros(torch::CUDA(at::kFloat), {batch, channel, height});
  to : auto max_val = at::zeros( {batch, channel, height}, torch::CUDA(at::kFloat));
  ```
  ### setup
      python setup.py install (--user)

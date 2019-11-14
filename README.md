# darknet_kannada_mnist

Training cifar for Kannada_MNIST dataset on darknet.

# requirement

- darknet
- opencv

# dataset

```
Kannada MNIST dataset is provided in data folder, extract it before training
```

# train

```
run train.cmd
```

# predict

```
run predict.cmd
```

# output

```
darknet.exe classifier predict cfg/mnist.dataset cfg/cifar_km.cfg backup/cifar_km_50000.weights data/img/valid/v_07993_c3.png
 compute_capability = 500, cudnn_half = 0
   layer   filters  size/strd(dil)      input                output
   0 Crop Layer: 28 x 28 -> 28 x 28 x 3 image
shift: Using default '0.000000'
   1 conv    128       3 x 3/ 1     28 x  28 x   3 ->   28 x  28 x 128 0.005 BF
   2 conv    128       3 x 3/ 1     28 x  28 x 128 ->   28 x  28 x 128 0.231 BF
   3 conv    128       3 x 3/ 1     28 x  28 x 128 ->   28 x  28 x 128 0.231 BF
   4 max                2x 2/ 2     28 x  28 x 128 ->   14 x  14 x 128 0.000 BF
   5 dropout       p = 0.50                  25088  ->   25088
   6 conv    256       3 x 3/ 1     14 x  14 x 128 ->   14 x  14 x 256 0.116 BF
   7 conv    256       3 x 3/ 1     14 x  14 x 256 ->   14 x  14 x 256 0.231 BF
   8 conv    256       3 x 3/ 1     14 x  14 x 256 ->   14 x  14 x 256 0.231 BF
   9 max                2x 2/ 2     14 x  14 x 256 ->    7 x   7 x 256 0.000 BF
  10 dropout       p = 0.50                  12544  ->   12544
  11 conv    512       3 x 3/ 1      7 x   7 x 256 ->    7 x   7 x 512 0.116 BF
  12 conv    512       3 x 3/ 1      7 x   7 x 512 ->    7 x   7 x 512 0.231 BF
  13 conv    512       3 x 3/ 1      7 x   7 x 512 ->    7 x   7 x 512 0.231 BF
  14 dropout       p = 0.50                  25088  ->   25088
  15 conv     10       1 x 1/ 1      7 x   7 x 512 ->    7 x   7 x  10 0.001 BF
  16 avg                             7 x   7 x  10 ->     10
  17 softmax                                          10
  18 type: Using default 'sse'
cost                                             10
Total BFLOPS 1.625
 Allocate additional workspace_size = 26.22 MB
Loading weights from backup/cifar_km_50000.weights...
 seen 64
Done! Loaded 19 layers from weights-file

 try to allocate additional workspace_size = 26.22 MB
 CUDA allocate done!
28 28
valid/v_07993_c3.png: Predicted in 0.039000 seconds.
3: 0.999998
7: 0.000001
5: 0.000001
6: 0.000000
2: 0.000000
```
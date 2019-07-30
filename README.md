The first test uses a modified version of the  KANN library for a pure-C inference using a small CNN.

The DNN inference in KANN can be built from source and executed using four commands:
```
cd kann; make; cd examples
./mnist-cnn -i kann-models/mnist-cnn.kan kann-data/mnist-test-x.knd.gz
```
This modified inference script evaluates one image (the first image in the MNIST test set).

The region of interest is the function call performing the inference: https://github.com/skoppula/approximate-memory-tests/blob/master/kann/kann.c#L976. There are print statement delineating the RoI. There are also no system calls in this region of interest, as verified using strace.

The original KANN library can be found at https://github.com/attractivechaos/kann/.

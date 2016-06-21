# tensorgraph
Tensorgraph is an **tensorflow example** to show
- How to generate checkpoint, graph.pb, tensorboard.
- How to use checkpoint and graph.pb to merge to freeze graph. (not finished yet)
- How to load graph with tensorflow c++ api and do the prediction.

# Requirement
- tensorflow installation, https://www.tensorflow.org/ <br> go to "GET STARTED" --> "installing from source"
- bazel installation, http://www.bazel.io/docs/install.html <br>

# gengraph
How to generate checkpoint, graph.pb, tensorboard. <br>
The directory struct is
```
mnist.py
board/
models/
```
After run
```
$ python mnist.py
```
The directory struct will be expected to
```
mnist.py
board/
    event.out.tfevents
models/
    graph.pb
    model.ckpt
Mnist_data/
    ...
```
# loadgraph
How to load graph with tensorflow c++ api and do the prediction. <br>
Put the directory to tensorflow source code.
Here is the final directory structure:
```
tensorflow/tensorflow/loadgraph
tensorflow/tensorflow/loadgraph/mnist.cc
tensorflow/tensorflow/loadgraph/MNIST.h
tensorflow/tensorflow/loadgraph/BUILD
```
Compile and Run
```
From inside the project folder call $bazel build :mnistpredict
From the repository root, go into bazel-bin/tensorflow/loadgraph.
Copy the frozen_graph.pb and Mnist_data to bazel-bin/tensorflow/loadgraph
Then run ./mnistpredict and check the output
```
# Reference
[MNIST_Loader](https://github.com/krck/MNIST_Loader) <br>
[Load graph with tensorflow c++ api](https://medium.com/jim-fleming/loading-a-tensorflow-graph-with-the-c-api-4caaff88463f#.chz3r27xt)



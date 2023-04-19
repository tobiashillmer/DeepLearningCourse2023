
Exercise Sheet Deep Learning
Part1: Foundations of Deep Networks
Summer 23
This sheet includes a theoretical part and a practical assignment of the first part of the
lecture Deep Learning (Foundations). It should be handed in as pdf in groups of three via
ekvv-Moodle until 20.4.23. at 10.a.m (sharp). Please include a link to the code (e.g. Colab)
name1: Tobias Hillmer
name2: Lukas Schubert
name3: Yasar Plückebaum
PARTI – THEORY: For the following, you might answer only YES/NO (or abstain),
or you can add short arguments (at most two lines per question). If you are not sure, it is
better to abstain.
1. The following properties are shared in between deep and shallow networks:
- Universal approximation capability. -> TRUE
- Efficiency of training in the sense of finding solutions with minimum training
error in polynomial time. -> False
- At some point, larger networks lead to overfitting. -> True
- The number of fundamentally different functions which can be represented sca-
les linearly with the number of model parameters. -> False


2. In deep network training, the following tricks help to avoid numeric problems in
end-to-end training:
- using fully convolutional networks; -> False
- change of activation function to ELU; -> True
- including pooling operator; -> False
- Combining Batch normalization and Dropout; -> FALSE(don't combine them)



3. The following network architectures fulfill the property ... . . .
- networks with convolutions involved in some layers can deal with input images
of arbitary size -> False, the network would need to be fully convolutional
- residual networks are invertible by means of function inversion -> True, with iterative correction
- One shot learning via Siamese Twin architectures learns new classes without
any given labeled sample -> False, Siamese Twin network work by learning differences between classes. With unlabeled data siamese twin networks can only cluster und not classify. For true classification on labeled data ot least one labeled data point is necessary.
- Deep adaptation networks perform transfer learning towards a different input
representation of a problem. -> False


4. The following networks from the model zoo approach the task:
- YOLO for one shot learning -> No
- OpenPose for visual question answering -> No
- Alphafold for playing games -> No
- Inception for image classification/recognition -> Yes


5. The following is true:
- A valid pooling operator is to average. -> True, another valid operator is to maximize.
- U-net architectures can be used with residual connections to obtain an invertible
function. -> True
- Fully convolutional architectures can deal with inputs of different sizes -> True
- ADAM refers to an extension of SGD where the expectation and variance are
normalized to Gaussian one. -> False


PARTII – PRACTICE: You can use code and models which are publicly available,
please clearly reference all sources and tools. Please give a link to your code (e.g. colab).
The length of the answer is limited to one page in total for the description of both parts
including images. Please provide: short description what you did, how it is done, what is
the result. Please be prepared to present the solution in the exercises.

[LinkToRepo](https://github.com/tobiashillmer/DeepLearningCourse2023/blob/main/Exercises/1_foundations/deep_learning_1_practical.ipynb)

1. Take the Fashion MNIST data set and a suitable model architecture. Display the
effect of the choice of the activation function, i.e., investigate different learning and
generalization behavior if sgd or a modern activation function (e.g. relu, selu, ...) is
used. Compare the behavior of at least three different activation functions.

We can see in the Jupyter-Notebook, that the Network performs similar for most modern activation function, with the SELU function performing best. In this case the network even performs similar for no activation function, which suggest that a similar performance could also be archived using only on dense layer. Only the sigmoid activation does not yield good results. There the network collapses an classifies everything as a T-Shirt.


2. Take the same setup and the ADAM optimizer, display the result of the choice of
different batch sizes for mini-batch training. Take at least three choices and shortly
discuss the differences.





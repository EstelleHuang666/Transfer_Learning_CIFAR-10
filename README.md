# Transfer_Learning_CIFAR-10
Using TensorFlow and the idea of transfer learning to trian over the dataset of CIFAR-10.

First of all, I would like to express my upmost thanks from the bottom of my heart to Scott Thompson, the author of original project, though it takes me quite a long time to correct some bugs caused by the update in TensorFlow or other reasons. This project is improved based on his code.
https://medium.com/@st553/using-transfer-learning-to-classify-images-with-tensorflow-b0f3142b9366


## Pre-training
Download the already trained Inception v3 based on ImageNet from http://download.tensorflow.org/models/image/imagenet/inception-2015-12-05.tgz. Put the classify_image_graph_def.pb under the path directed by README.md.
Download CIFAR-10 from http://www.cs.toronto.edu/~kriz/cifar.html. Put these data uder the path directed by README.md.

If you have the interest to complete the pre-training process by yourself, refer to the following steps:
Step 1: download https://github.com/tensorflow/tensorflow, which is quite different from the lib you get by "pip install tensorflow".
Step 2: cd /tensorflow/examples/image_retraining/retrain.py.
Step 3: download a dataset, saying we use https://github.com/caicloud/tensorflow-tutorial/tree/master/Deep_Learning_with_TensorFlow/datasets/flower_photos. Put the downloaded file into the path in Step2.
Step 4: 
```
python retrain.py --image_dir flower_photos/
```
Step 5: for Mac, find the .pb files in the /tmp path, using tensorboard to visualize it.
```
python tensorflow/tensorboard/tensorboard.py --logdir=/tmp/mnist_logs
```
Input http://localhost:6006 in the browser.

## Get the Output of Pool_3
For this project, you have to calculate the value at layer pool_3 first. In this case, we need to proceed serialize_data() in transfer_cifar10_softmax.py, getting 4 .npy files named by current time. Correct the name of these files in load_pool3_data().

## Train the Last Fully Connected Layer
Run the transfer_cifar10_softmax.py, and you could get the output. The design of the code structure is somehow inefficient, under this circumstance, further improvement will be made in future.

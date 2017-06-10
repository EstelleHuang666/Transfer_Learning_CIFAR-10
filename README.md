# Transfer_Learning_CIFAR-10
Using TensorFlow and the idea of transfer learning to trian over the dataset of CIFAR-10.

## Pre-training
Download the already trained Inception v3 based on ImageNet from http://download.tensorflow.org/models/image/imagenet/inception-2015-12-05.tgz. Put the classify_image_graph_def.pb under the path directed by README.md.

If you have the interest to complete the pre-training process by yourself, refer to the following steps:
Step 1: download https://github.com/tensorflow/tensorflow, which is quite different from the lib you get by "pip install tensorflow".
Step 2: cd /tensorflow/examples/image_retraining/retrain.py.
Step 3: download a dataset, saying we use https://github.com/caicloud/tensorflow-tutorial/tree/master/Deep_Learning_with_TensorFlow/datasets/flower_photos. Put the downloaded file into the path in Step2.
Step 4: 
```
python retrain.py 
```

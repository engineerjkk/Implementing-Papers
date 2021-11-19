# AlexNet in TensorFlow

This repository comes with AlexNet's implementation in TensorFlow. AlexNet is the winner of the ILSVRC-2012 Competition. 

The original model introduced in the paper used two separate GPUs for architecturing. That was due to the lack of GPU resources (memory) at the time. Because the limitation is no longer applicable for the current GPU technology for the AlexNet, this repository's implementation merged two separate models allocated into two separate GPUs into one.

![image](https://user-images.githubusercontent.com/76835313/142556269-9016be0a-77bd-48b9-99bf-d5dbe697fc89.png)
![image](https://user-images.githubusercontent.com/76835313/142556275-0ca8fa8f-887e-49db-b419-c79f1eda0b53.png)

## Required Packages
- numpy
- tensorflow-gpu (>2.3)

## Usage
- From command line
  -  Will download CIFAR-10 dataset and pre-processing of it, and run the training on AlexNet. It will produce the checkpoint file for performing inference later.
```shell
AlexNet.ipynb
```

## Resources

- **AlexNet.pdf :** My own summary focused on implementation detail
- **AlexNet.ipynb :** Experimental workflow code on CIFAR-10 dataset
- **External Checkpoint files**
  - providing pre-trained checkpoint file on CIFAR-10 dataset
  - [Download Link](https://drive.google.com/drive/folders/1-bUYAWx6dQ8b5Nw6O_juvZwnNVk-M1Qu?usp=sharing)

## Overall Architecture
**1. Input Layer of Image Size (224 x 224 x 3)**

**2. Convolutional Layer (96 x (11 x 11 x 3)) + stride size of 4**
   - Bias with constant value of 1
   - ReLU Activation
   - Local Response Normalization
   - Max Pooling (Overlapping Pooling)

**3. Convolutional Layer (256 x (5 x 5 x 48))**
   - ReLU Activation
   - Local Response Noramlization
   - Max Pooling (Overlapping Pooling)

**4. Convolutional Layer (384 x (3 x 3 x 128))**
   - Bias with constant value of 1

**5. Convolutional Layer (384 x (3 x 3 x 192))**
   - Bias with constant value of 1

**6. Convolutional Layer (256 x (3 x 3 x 192))**
   - Max Pooling (Overlapping Pooling)

**7. Fully Connected Layer (4096)**
   - Bias with constant value of 1
   - Dropout

**8. Fully Connected Layer (4096)**
   - Bias with constant value of 1
   - Dropout

**9. Fully Connected Layer (1000)**

## Training
- **Optimizer (Implementation) :** AdamOptimizer

## References
- [ImageNet Classification with Deep Convolutional Neural Networks](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf) (Original Paper)
- [AlexNet Summary files](https://github.com/engineerjkk/implementing-Papers/tree/main/02.AlexNet(2012)/AlexNet%20Summary)
- [AlexNet tf-gpu==1.7 from scratch](https://github.com/engineerjkk/implementing-Papers/tree/main/02.AlexNet(2012)/AlexNet%20tf-gpu%3D%3D1.7%20from%20scratch)
- [AlexNet tf-gpu==2.3](https://github.com/engineerjkk/implementing-Papers/tree/main/02.AlexNet(2012)/AlexNet%20tf-gpu%3D%3D2.3)
- [CNN reference](https://github.com/engineerjkk/implementing-Papers/blob/main/02.AlexNet(2012)/High-Performance%20Neural%20Networks%20for%20Visual%20Object%20Classification.pdf)
- [Comparison with Lenet and AlexNet.pdf](https://github.com/engineerjkk/implementing-Papers/blob/main/02.AlexNet(2012)/Comparison%20with%20Lenet%20and%20AlexNet.pdf)
- [CNN_Architectures.pdf](https://github.com/engineerjkk/implementing-Papers/blob/main/02.AlexNet(2012)/CNN_Architectures.pdf)
- Local Response Normalization
  - https://stats.stackexchange.com/questions/145768/importance-of-local-response-normalization-in-cnn

# Semantic Segmentation
### Introduction
In this project, you'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Result
I followed first the walktrough shown in the classroom. Then I implemented the layers function and added to every layer a kernel initializer with standard deviation of 0.01.
In the optimize function I calculate the cross entropy loss like shown in the classroom. The I used the Adam optimizer.
In the training function the sesson runs with a learning rate of 0.001.
I choosed 20 epochs and a batch size of 2.
The average loss decreases over time:
EPOCH 1
Average loss: 7.057241061638141

EPOCH 2
Average loss: 0.555429138191815

EPOCH 3
Average loss: 0.4765240321899282

EPOCH 4
Average loss: 0.37865559705372515

EPOCH 5
Average loss: 0.27543436103853686

EPOCH 6
Average loss: 0.22817311348586247

EPOCH 7
Average loss: 0.20538950038367304

EPOCH 8
Average loss: 0.1853722806120741

EPOCH 9
Average loss: 0.1650569324863368

EPOCH 10
Average loss: 0.17491112084224306

EPOCH 11
Average loss: 0.150687311281418

EPOCH 12
Average loss: 0.1383171381107692

EPOCH 13
Average loss: 0.13818232648331544

EPOCH 14
Average loss: 0.12862954774293406

EPOCH 15
Average loss: 0.11738070645209016

EPOCH 16
Average loss: 0.11104655396835557

EPOCH 17
Average loss: 0.11347324827621723

EPOCH 18
Average loss: 0.10706853530016439

EPOCH 19
Average loss: 0.10999992471830598

EPOCH 20
Average loss: 0.09840402662240226

### Setup
##### GPU
`main.py` will check to make sure you are using GPU - if you don't have a GPU on your system, you can use AWS or another cloud computing platform.
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder  (**all images from the most recent run**)
 
 ### Tips
- The link for the frozen `VGG16` model is hardcoded into `helper.py`.  The model can be found [here](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/vgg.zip).
- The model is not vanilla `VGG16`, but a fully convolutional version, which already contains the 1x1 convolutions to replace the fully connected layers. Please see this [post](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/forum_archive/Semantic_Segmentation_advice.pdf) for more information.  A summary of additional points, follow. 
- The original FCN-8s was trained in stages. The authors later uploaded a version that was trained all at once to their GitHub repo.  The version in the GitHub repo has one important difference: The outputs of pooling layers 3 and 4 are scaled before they are fed into the 1x1 convolutions.  As a result, some students have found that the model learns much better with the scaling layers included. The model may not converge substantially faster, but may reach a higher IoU and accuracy. 
- When adding l2-regularization, setting a regularizer in the arguments of the `tf.layers` is not enough. Regularization loss terms must be manually added to your loss function. otherwise regularization is not implemented.
 
### Using GitHub and Creating Effective READMEs
If you are unfamiliar with GitHub , Udacity has a brief [GitHub tutorial](http://blog.udacity.com/2015/06/a-beginners-git-github-tutorial.html) to get you started. Udacity also provides a more detailed free [course on git and GitHub](https://www.udacity.com/course/how-to-use-git-and-github--ud775).

To learn about REAMDE files and Markdown, Udacity provides a free [course on READMEs](https://www.udacity.com/courses/ud777), as well. 

GitHub also provides a [tutorial](https://guides.github.com/features/mastering-markdown/) about creating Markdown files.

# ERA Session 5 Assignment
Zubair Hawa<br>



Table of contents
1. [model.py](#modelpy)
    - [About the model](#about-the-model)
2. [utils.py](#utilspy)
    - [train procedure](#the-train-procedure)
    - [test procedure](#the-test-procedure)
    - [plot_graphs procedure](#the-plot_graphs-procedure)
3. [S5.ipynb](#s5ipynb)
    - [Working of the S5.ipynb file](#working-of-the-s5ipynb-file)
    
## model.py
### About the model
This file contains the Neural Network which defines how our model works and how it will be learning data and the patterns. The total parameters in this model would be 593,200 and the number of receptive fields would be 16.

## utils.py
### The train procedure

The train procedure takes 5 parameters. Each parameter is described in this table.
| Parameter name | Description                                                                                   |
|----------------|-----------------------------------------------------------------------------------------------|
| model          | The Neural Network model on which to train                                                    |
| device         | The device that the network will use to train. (Example- CUDA,CPU,GPU)                        |
| train_loader   | The DataLoader object that contains the dataset to train the model on.                        |
| optimizer      | The optim.SGD object that defines the learning rate and learning momentum among other things. |
| criterion      | The loss function that will be used to define the weights.                                    |

The train procedure will also display a progress bar as the training takes place. The progress bar will contain information about accuracy and batch ID.

### The test procedure
The test procedure takes 4 parameters. Each parameter is described in this table.
| Parameter name | Description                                                                                   |
|----------------|-----------------------------------------------------------------------------------------------|
| model          | The Neural Network model on which to test.                                                    |
| device         | The device that the network will use to test. (Example- CUDA,CPU,GPU)                        |
| test_loader   | The DataLoader object that contains the dataset to test the model on.                        |
| criterion      | The loss function that will be used to define the weights.                                    |

The test procedure will also display a progress bar as testing takes place. The progress bar will contain information about accuracy and batch ID. <br>
This procedure is what will enable us to see whether our model is accurate enough or not.

### The plot_graphs procedure

This procedure will plot graphs when called. These graphs will show us how the model fared in training and testing. Will show loss and accuracy for both, training and testing.

## S5.ipynb
### Working of the S5.ipynb file
Each code snippet, or codeblock, performs a specific task.<br>
Some codeblocks also have a output after them. A clear font and background colour difference is present to make a distinction. <br>
I'll cover each codeblock in this README file. <br>
1. The first codeblock imports all necessary libraries including torch and torchvision. It also imports our model from the model.py file and the entire utils module from the utils.py file.
2. The second codeblock initializes the model. In this process, the device to be used is set and a summary of the model is printed. Each layer is documented in the summary with the number of parameters after each layer and the output shape shown. <br>
The final estimated total size is also shown.
3. Here, our transformations are defined. These transformations will be applied to the data when used for training/testing. Since these transformations would be unique to each dataset, it makes sense to have it in the S5.ipynb file rather than the utils.py file.
4. In the fourth codeblock, we define our dataset which is the MNIST dataset. We will be defining both, training and testing datasets here.
5. The fifth codeblock defines our batch_size along with the DataLoader objects. This is done so we can have an iterator for our MNIST images.
6. This codeblock plots 12 random MNIST images from the DataLoader defined earlier.
7. Our actual training and testing takes place here. This is where we will be figuring out whether our model is accurate enough or not.
8. This is where the training and testing graphs are plotted using the plot_graph procedure from utils.py. This will help us figure out whether we need to reduce learning rate amongst other things. 
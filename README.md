How to run the code
There are two approach to run this code. First one is to run cifar10_train.py and then its start to train with 50000 images.
Second run cifar10_eval.py to evaluate your trained checkpoints. I already doing the train section and upload it to wetransfer.com 
(download link: https://we.tl/rF4eLjXZpx ) and also I uploaded it to LMS system in the cifar10_train folder you can easily Copy saved 
checkpoints (cifar10_train folder) to “Current Drive:\tmp” and run the cifar10_eval.py from src and get the accuracy.


My Network Designs 
I designed my two networks in the cifar10.py with names of inference and inference1


Training Description
For training, we additionally apply a series of random distortions to artificially increase the data set size:
•	Randomly flip the image from left to right.
•	Randomly distort the image brightness.
•	Randomly distort the image contrast.
The usual method for training a network to perform N-way classification is multinomial logistic regression, aka. softmax regression. Softmax regression applies a softmax nonlinearity to the output of the network and calculates the cross-entropy between the normalized predictions and a 1-hot encoding of the label. For regularization, we also apply the usual weight decay losses to all learned variables. The objective function for the model is the sum of the cross entropy loss and all these weight decay terms, as returned by the loss() function.
For launching and training the model you can use this command in command line:
python cifar10_train.py
The first time you want to run, CIFAR-10 dataset is automatically downloaded and save to “current drive:\tmp\cifar10_data”.
cifar10_train.py periodically saves all model parameters in checkpoint files but it does not evaluate the model. The checkpoint file will be used by cifar10_eval.py to measure the predictive performance


Evaluating a Model
       The model is evaluated by the script cifar10_eval.py. It constructs the model with the inference() function and uses all 10,000 images in the evaluation set of CIFAR-10.
You can use this command to evaluate:
python cifar10_eval.py
the expected output should like this:
2017-05-06 19:57:23.443634: precision @ 1 = 0.930
That means I get 93% accuracy.

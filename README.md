# Assignment Session 2.5 PyTorch 101 

## Problem Desription

![image](https://user-images.githubusercontent.com/120099863/209846784-f75aaa07-2b7c-48b7-9345-141f5fb51aeb.png)

## Design
For this problem 2 datasets are merged in Class RandomNo_MNIST:
1. MNIST: Downloaded using torchvision.datasets.MNIST
2. Random Number: Method __getitem__ is using torch.randint for Random number generation. Same is One hot encoded to be used as data in a fully connected layer.

RandomNo_MNIST is returning data of image & random number and their respective labels.

Class Network is defined for Neural Network with 2 input & 2 output. Approach used in this Network is to get a prediction of MNIST dataset first and concatenate that output with a random number. MNIST output of 10 features and One hot encoding (F.one_hot) of random number are concatenated using torch.cat. There will be 20 input features from the concatenated layer and this layer is passed to a fully connected layer (100 in this case) & finally to the output layer (19 output).

MNIST prediction and Sum prediction are returned as output. First loss is calculated individually using F.cross_entropy for both of them (because both are one hot encoded) and then it is summed up to get total loss. After this network is adjusted for total loss gradient.

Results of this are evaluated for MNIST & Sum individually on Train & Test dataset. <b>It was observed that after the initial epoch Sum results become tightly linked with MNIST prediction.</b>

## Accuracy
After 10 epoch Accuracy for both MNIST & Sum was 99.69 % for Training set and 99.21% for Test set.

Training Log:
![image](https://user-images.githubusercontent.com/120099863/211018312-0b517495-a0a7-4e1d-8809-e39691d84446.png)

Test Set Result:
![image](https://user-images.githubusercontent.com/120099863/211018397-739e2a2d-2dfe-4f8e-b856-6ca0e2cf22e9.png)






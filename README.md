# Assignment Session 2.5 PyTorch 101 

## Problem Desription

![image](https://user-images.githubusercontent.com/120099863/209846784-f75aaa07-2b7c-48b7-9345-141f5fb51aeb.png)

## Design
For this problem 2 datasets are downloaded/created:
1. MNIST: Downloaded using torchvision.datasets.MNIST
2. Random Number: Dataset class RandomNo created. Method __init__ is using torch.randint for Random number generation and __getitem__ to get data in return

While training the model there is For loop on MNIST DataLoader and <b>iter</b> on DataLoader for RandomNo for looping to the next batch.

Approach used in this Network is to get a prediction of MNIST dataset first and concatenate that output with a random number. One hot encoding (F.one_hot) is used on both prediction & random number and torch.cat is used for concatenation. After this there will be 20 input features from the concatenated layer and this layer is passed to a fully connected layer (100 in this case) & finally to the output layer (19 output).

Both of these outputs are returned and loss is calculated individually using F.cross_entropy for both of them because both are one hot encoded. Loss is calculated individually and then it is summed up to get total loss. After this network is adjusted for total loss gradient.

Results of this are evaluated for MNIST & Sum individually. <b>It was observed that after the initial epoch Sum results become tightly linked with MNIST prediction.</b>

## Accuracy
After 15 epoch Accuracy for both MNIST & Sum was 99.8% (59,881/60,000) 

Training Log:
![image](https://user-images.githubusercontent.com/120099863/209853271-9fa02fce-6b14-43dc-ba79-3e9fce319a40.png)



# Spacesense Eurosat

Constrains of the current solution:

* Class imbalances: some classes had more pictures than others (for example Industrial had 2501 items while annual crop had 3001 items)

* Model architecture: plays a vital role in the training of CNNs, but it can be computationally expensive. Due to limited power resources on my computer, I had to significantly simplify my model architecture from 6 convolutional blocks to just 2. Furthermore, I had to decrease the number of epochs to 15, which is the number of times the model processes the dataset. I also experimented with using Google's collab GPU and TPU, but the estimated time per epoch was roughly 1 hour and 30 minutes.

* Quality of the image: in some cases it may be even hard for the human eye to detect which class was which. 

Before delving into the changes to enhance performance, I want to share two useful techniques that aided my model training. Firstly, data augmentation was employed by randomly rotating images(amongst other things) in the training set to increase the ability of the model to generalize on unseen data. Secondly, adding a BatchNormalization layer before each convolutional block normalized the inputs of each layer. Implementing both techniques increased the accuracy on the validation set from 60% to 81%.

Improvements of the current model:

* To enhance the model's performance, I would increase the number of convolutional blocks from 2 to 6. While running a Gridsearch for hyper-parameter tuning would be the best approach, it could be computationally expensive. For kernel and pool size, smaller architectures have been show to generally performance better and retain more information. Additionally, I would decrease the stride from 5 to 1 to achieve the highest quality possible (the number of steps the sliding window takes). Experimenting with other activation functions like elu, selu, etc. and increasing the number of layers and neurons in the classifier while adding dropout to combat overfitting would also be beneficial. However, it's crucial to keep the output layer to 10 neurons, one per class, to avoid errors.

Lastly, I would explore transfer learning, as mentioned in the notebook Part 1.ipynb

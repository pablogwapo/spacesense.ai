# Spacesense Eurosat

Constrains of the current solution:


* Class imbalances: some classes had more pictures than others (for example Industrial had 2501 items while annual crop had 3001 items)

* Model architecture: Trainning CNNs can be quite computationally expensive, and due to low power 
resources on my computer I had to signifantly reduce the structure of my model from 6 convolutional blocks to 2. I also had to reduce the number of epochs
(the number of times the model goes through the dataset) to 15. I tried using Google's collab GPU and TPU but the estimated time per epoch was around 1:30h. 


Due to low power resources of my computer I was only able to train to convolutional blocks over 15 epochs. 






* Quality of the image: in some cases it may be even hard for the human eye to detect which class was which. 

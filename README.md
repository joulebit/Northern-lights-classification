# Northern-lights-classification
Use CNN to classify images that contain Northern lights and sort them into a seperate folder.


![image](https://user-images.githubusercontent.com/45593399/85561597-04965a00-b62c-11ea-90cc-88ca75d38bbb.png) ![image](https://user-images.githubusercontent.com/45593399/85561943-550db780-b62c-11ea-8d11-5ff4900c05a2.png)  
Left image contains northern light while the right image does not. How capable is a Convolutional Neural Network at distinguishing these two cases?  

## Transfer Learning
Given the vast compute and time resources required to develop neural network models on computer vision, i will take advantage of a pretrained ResNet50. Transfer learning is a machine learning technique where a model trained on one task is re-purposed on a second related task. It is done by removing the last layer which does the classification, and replacing it with your own last layer with the parameters you want to classify. Then you can train it on your new categories with just a fraction of the dataset. [Here is a link to the pretrained resnet50 network.](https://www.kaggle.com/alexisbcook/resnet50)

## Data Collection
Since i took advantage of transfer learning, i could get a decent result by having way less training data.  
The two categories required are training images and validation images, both of which are further categorized into northern lights pictures and not northern light pictures.  

### Training images
208 northern light images from a family members collection were used, a decent portion came in groups with the same foreground and and almost same background.  
237 images not containing northern light were also used to help the model distinguish the difference. These images contained various settings and motives (e.g forrest, hiking, kayaking, flowers, mountains, houses, cities), basically all my newest photos.

### Validation images
40 validation images were downloaded from google as to have no other relation with the training data than if it contained northern lights. 20 of them were from the top results when googling northern light, and the other half was from different settings not containing northern lights. 


## Data Augmentation
One can artificially increase the amount of aviable images by using scaling, flipping and rotation. In this project a scaling up to 0.1 and horizontal flipping were used.
![image](https://user-images.githubusercontent.com/45593399/85801182-9d1efe00-b742-11ea-9441-7c6951df2146.png)

## Results
The validation accuracy achieved 92.5%, which means it correctly labeled 37/40 images. This is  better than i originally expected, but there is definitively room for improvement
![image](https://user-images.githubusercontent.com/45593399/85801668-a9578b00-b743-11ea-8e93-efcd308f54f9.png)

## Improvements
The most obvious improvement would be to have a better and more varied selection of images not containing northern light for the training set, since it currently only contains my most recent photos.  
The other improvement would be to expand the validation set of pictures. I tried to trick the model with different images from nature which could look similar to a northern light night, instead of validating it on the sort of random pictures found in the training data. So for real world application, the model work better.


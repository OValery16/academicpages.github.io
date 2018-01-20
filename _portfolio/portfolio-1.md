---
title: "Gender and age classification in videos and images"
excerpt: "This project aims to extract people's faces from an image/video and to predict their gender and age. All my code and the weights can be downloaded on my [Github](https://github.com/OValery16/gender-age-classification)<br/><img src='/images/selfi2_detectedsmall.jpg'>"
collection: projects
permalink: /projects/p2
---

This project aims to extract people's faces from an image/video and to predict their gender and age. All my code and the weights can be downloaded on my Github.

First, I train a YOLO model to perform face detection. Most of YOLO model seems to be implemented on the Darknet framework. However, a direct conversion of the weights obtained with darknet leads to relatively poor performance. As a result, I ended up retraining YOLO for face detection (I initialized my weight to the standard YOLO implementation). 

Then, I stacked a gender/age detection CNN. My network outputs two information: the class of the gender (Male/Female) and the age class. For the age, as mentioned in my previous email, it is very hard to get the exact face/age mapping. Most of the dataset I found (for example, IMDB) are relatively small. As a result, my approach here is to output an interval (['(0, 2)','(4, 6)','(8, 12)','(15, 20)','(25, 32)','(38, 43)','(48, 53)','(60, 100)']) instead of the exact age ([0,100]) The model that I used is INCEPTION_V3 as implemented in tensorflow. (I retrain it using their weights) 

My application works like this:


![](/images/architecture.JPG?raw=true)



## Know prediction errors

Several prediction errors could happen in the following case:
* The face is too far from the camera
	* The picture used in the training mostly includes people that are relatively closed to the camera
* The picture includes many character that are very closed to each other
	* The picture used in the training mostly includes people are not too closed for each other
* The face is very closed to the border
	* Our system consists in the combinasion of 2 neural networks. The first one extract the faces as a square image, the second one resize them to the correct input size and predicts the corresponding label of each of them. Howeve if the face is closed to the picture's border, the extracted face may not be a square size image, wich force our system to distord the image in order to make it fit in our model. It can lead to pottential errors.
* The lighting condition are very different from our training set
	* The picture used in the test set should have similar distribution as the validation set.
	
## Note:

In deep learning, it important to know that the training set should cover sufficiently the scenarios that you want to score later on. If the classifier sees fully new concepts or contexts it is likely to perform badly. Just a few examples:

* You train only on images from a constraint environment (say, indoor) and try to score images from a different environment (outdoor).
* You train only on images of a certain make and try to score others.
* Your test images have largely different characteristics, e.g. with respect to illumination, background, color, size, position, etc.
* Your test images contain entirely new concepts.

As a result, we invite the reader to fine tune our model in case it makes some prediction errors with their test set (see previous section). Another parameter that ca be adjusted is size of the face that is extracted (go to "utils.py" and search for 'getFacesList' and adjust the size of maxDist)
	
* Each label is written like gender, (age_interval)	
	* The exact age cannot be guessed without large training dataset (which we don't have)
	* Instead we guess the age intervale
		
# The following pictures are example of input/output:



Input            |  Output
:-------------------------:|:-------------------------:
![](/images/Capture.jpg?raw=true)  |  ![](/images/Capture_detected.jpg?raw=true)
![](/images/image_extracted1.jpg?raw=true)  |  ![](/images/image_extracted1_detected.jpg?raw=true)
![](/images/webcam.jpg?raw=true)  |  ![](/images/webcam_detected.jpg?raw=true)
![](/images/olivier.jpg?raw=true)  |  ![](/images/olivier_detected.jpg?raw=true)
![](/images/webcam_test.jpg?raw=true)  |  ![](/images/webcam_test_detected.jpg?raw=true)
![](/images/big_bang_theory4.jpg?raw=true)  |  ![](/images/big_bang_theory4_detected.jpg?raw=true)
![](/images/big_bang_theory2.jpg?raw=true)  |  ![](/images/big_bang_theory2_detected.jpg?raw=true)
![](/images/big_bang_theory5.jpg?raw=true)  |  ![](/images/big_bang_theory5_detected.jpg?raw=true)
![](/images/friends.jpg?raw=true)  |  ![](/images/friends_detected.jpg?raw=true)
![](/images/game-of-thrones.jpg?raw=true)  |  ![](/images/game-of-thrones_detected.jpg?raw=true)
![](/images/how_I_met_your_mother.jpg?raw=true)  |  ![](/images/how_I_met_your_mother_detected.jpg?raw=true)
![](/images/selfi.jpg?raw=true)  |  ![](/images/selfi_detected.jpg?raw=true)
![](/images/selfi2.jpg?raw=true)  |  ![](/images/selfi2_detected.jpg?raw=true)







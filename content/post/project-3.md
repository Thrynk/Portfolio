---
date: 2020-10-11T00:00:00-00:00
description: "Project to build a Deep Learning AI that recognize if human has a safety mask or not, and if this mask is well placed"
featured_image: "/images/masked-person.jpg"
tags: ["Deep Learning", "Covid", "Safety Mask"]
title: "2020-10 : Masked recognition AI"
---

In this school project, we are a team of 5 students, and we are challenged to program an AI that will understand thanks to a photo if a human is wearing a safety mask or not, but also if this safety mask is well-worn

This project will help me discover Neural Networks, and Computer Vision.

# MaskProject

## Introduction 
The health crisis of COVID-19 (known as Coronavirus) striking the whole world, forced everybody to wear a mask. 
Besides governments efforts, the virus is still spreading. Indeed, some people don't wear their mask properly. In this project, we will propose to solve this problem with Deep Learning. 
Our algorithm will detect if someone wears or not a mask and if yes, if it is well worn. 


## State of the art
In the article : [A hybrid deep transfer learning model with machine learning methods for face mask detection in the era of the COVID-19 pandemic](https://www.sciencedirect.com/science/article/pii/S0263224120308289), they used a Deep Transferring Learning (ResNet50) as a feature extractor followed by a classical Machine Learning component like Decision Trees, SVM and Ensemble. The SVM classifier achieved 99.64% testing accuracy in their first dataset called RMFD (Real-world Masked Face Dataset), they used 10,000 images (5000 of masked faces and 5000 for unmasked faces). In SMFD (Simulated Masked Face Dataset containing 785 simulated masked faces and 785 unmasked faces), it achieved 99.49%, while in LFW (Labeled Faces in the Wild containing 13,000 simulated masked faces), it achieved 100% testing accuracy. 
    
Vladimir Iglovikov, Kaggle Grandmaster, used an efficient net (optimized convolutional network) to detect if the person is wearing a mask or not. He achieved 99.6 % of testing accuracy. Here is the link to his Github [facemask_detection](https://github.com/ternaus/facemask_detection). He merged different datasets : RMFD (Real-world Masked Face Dataset containing 5000 masked faces and 90,000 unmasked faces), [Medical mask dataset](https://humansintheloop.org/medical-mask-dataset/) containing 6000 images, [Face mask detection dataset](https://www.kaggle.com/andrewmvd/face-mask-detection) from Kaggle containing 853 images and the [VGGFace2](http://www.robots.ox.ac.uk/~vgg/data/vgg_face2/) containing more than 3.3 millions of images, usually used for face detection.
    
In this Medium's article : [COVID-19: Face Mask Detection using TensorFlow and OpenCV](https://github.com/mk-gurucharan/Face-Mask-Detection), he used a Convolutional Neural Network to predict if a person is wearing his mask or not, he achieved a 96.19 % testing accuracy with 2200 images in the training set and 551 images for the test dataset. Their original dataset contains 690 masked and 686 unmasked faces.

## Datasets 
We will use the [MaskedFace-Net](https://github.com/cabani/MaskedFace-Net) dataset. It contains 67,193 images with correctly masked faces and 69,823 images with incorrectly masked faces. 
The incorrectly masked faces is divided in three categories : 
- People only wearing the mask on their chin (6242 images)
- People only wearing the mask on their chin and mouth (57214 images)
- People only wearing the mask on their nose and mouth (6352 images)

Moreover, we will use the [FFHQ](https://github.com/NVlabs/ffhq-dataset) dataset for unmasked faces. 

Therefore, we have 5 classes to predict.

We will balance our dataset and pick :
- 6242 images of unmasked faces
- 6242 images of people wearing the mask on their chin
- 6242 images of people wearing the mask on their chin and mouth
- 6242 images of people wearing the mask on their nose and mouth
- 6242 images of people wearing the mask correctly

## Our choice
We chose to build our model with a CNN (Convolutional Neural Network) at first.
We will use only one neural network to predict the different classes and won't divide the problem into two parts (mask or not mask followed by if mask, is it correctly worn).
We will try different transfer learning models like ResNet architectures or VGG16/19.

We will compose different teams to test different transfer learning models :
- ResNet34 : achtrl
- ResNet50 : foukette
- VGG16 : Thrynk
- VGG19 : romainmeunier93 and FlonyxSly

## Preprocessing
We resized the images from 1024x1024 to 224x224 thanks to OpenCV, you can find our new dataset on [OneDrive](https://yncrea.sharepoint.com/:f:/r/sites/ProjetMasque/Documents%20partages/General/ResizedDataset?csf=1&web=1&e=7AEn3n). We chose this size in order to respect the input size of our different architectures. 

There is not much content now, because we just started the project. But I will update this project page during the project, so stay in touch !

[Link to the Github Repository](https://github.com/romainmeunier93/MaskProject/tree/vgg16)

## Results

The winning model is the vgg16 based on confusion matrices from each model.

Here is our final product demo (in French) :

<iframe src="https://www.linkedin.com/embed/feed/update/urn:li:ugcPost:6769545304338427904" height="1094" width="504" frameborder="0" allowfullscreen="" title="Embedded post"></iframe>
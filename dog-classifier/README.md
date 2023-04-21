# Write an Algorithm for a Dog Identification App

The goal of this project was to write an algorithm that accepts any image as an input and detects

1) if there is a human and if yes, what breed of dog the human looks like
2) if there is a dog and if yes, what breed it is

using OpenCv's Haar feature-based cascade classifier for human face detection and pre-trained image classification models for dog detection and classification.

## Structure

Step 0: Import Datasets 
- Human and dog datasets provided by Udacity

Step 1: Detect Humans 
- OpenCV's implementation of Haar feature-based cascade classifiers used to detect human faces in human dataset

Step 2: Detect Dogs 
- VGG16 pretrained on ImageNet used to detect dogs in both human and dog dataset

Step 3: Create a CNN to Classify Dog Breeds 
- A simpler version of ResNet50 created, trained, and tested on dog dataset

Step 4: Create a CNN to Classify Dog Breeds 
- Transfer learning from the pretrained ResNet50, best version of model parameters saved

Step 5: Write your Algorithm 
- Fine tuned model loaded and used to detect if there is a human or a dog face in the given image and predict what dog breed it resmbles

Step 6: Test Your Algorithm 
- The algorithm to detect human/dog faces and predict dog breed tested on sample images

# Blackpink Classifier

#### Aim: To build a Convolutional Neural Network (CNN) multi-classifier to classify the images of Blackpink members using keras.

#### _Brief Introduction to Blackpink:_
Blackpink is a 4-member female Korean pop band, consists of member Jisoo, Jennie, Rose and Lisa. This band debuted on 8th August 2016 under YG entertainment.

#### _Task:_
To classify the members of Blackpink accurately with their given labels (supervised learning).

#### _This repository contains:_
  - File Structure of the initial setup
  - Data Pre-processing
  - Training of Deep Neural Network
  
#### _File Structure:_
```
blackpink-classifier/
|-- datasets
  |-- y0_raw
        |-- <insert images of Blackpink member Jisoo>
    |-- y1_raw
        |-- <insert images of Blackpink member Jennie>
    |-- y2_raw
        |-- <insert images of Blackpink member Rose>
    |-- y3_raw
        |-- <insert images of Blackpink member Lisa>
|-- images
    |-- jennie1.jpg
    |-- jisoo1.jpg
    |-- lisa1.jpg
    |-- rose1.jpg
|-- Blackpink Classification.ipynb
|-- Data Pre-processing for Multi Classifier.ipynb
```

#### _Dataset outline:_
  - Scraped images from search engines
  - 500 images x 4 members = 2000 raw images
    1. 60-20-20 train-dev-test initial split => 300 train, 100 dev and 100 test images per class
    2. 300 train set images -- IMAGE AUGMENTATION (x6) --> 1800 train set images per class
    3. Total: 1800 train, 100 dev and 100 test images per class (approximately 90-5-5 split)
- In total: ~2000 images x 4 members = ~8000 images

#### _Main Files:_
- Blackpink Classification.ipynb
	- x6 Data Augmentation of the images (1 original + 5 augmented for each image)
	- Transfer learning: Loaded pre-trained model MobileNetV2
	- MobileNetV2 -> MAXPOOL -> Flatten -> Fully Connected 0 -> Dropout 20% -> Fully Connected 1
	- Accuracy:
		- Epochs: 20 | Batch Size: 32 | Train: 74.3% | Dev: 41.3% | Test: 42.5%
- Data Pre-processing for Multi Classifier.ipynb
	- Image Processing
		- Train-dev-test split
		- Resize Images
		- Data Augmentation
	- Generate HDF5 Files    
		- Convert to numpy data
		- Generate H5 Data
		- Check H5 Data
        
 #### _Approach Taken:_
1. Scrape images to obtain your dataset
2. Place the images into ./datasets according to the file structure above
3. Briefly checked the photos and scrape some Blackpink members' images from search engine such that these images do not appear in either of the sets
4. Place the images into the ./images folder as shown in the file structure above
5. Run Data Pre-processing for Multi Classifier.ipynb to obtain the train, dev and test .h5 datasets
6. Run Blackpink Classification.ipynb to obtain its accuracy

#### _Why is the dev and test accuracy so low?_
As the datasets are created by scraping images from search engines and then splitted randomly to train-dev-test set, there may be an issue of data mismatch, where the data in the train set comes from a different distribution from those that are in the dev set (eg. same person with different hair color, angle of images, background etc).

#### _Why is the train accuracy not within the 90% range?_
This might be due to a high bias issue where the algorithm is underfitting the model.
 
#### _References:_
- Andrew Ng's Deep Learning Specialisation: https://www.coursera.org/specializations/deep-learning
- Blackpink's Profile: https://kprofiles.com/black-pink-members-profile/
- Image Scraping Video: https://www.youtube.com/watch?v=T2kvOGq7P18

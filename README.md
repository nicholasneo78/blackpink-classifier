# Blackpink Classifier

#### Aim: To build a Convolutional Neural Network (CNN) multi-classifier to accurately classify images of kpop female group Blackpink members using keras.

#### _Brief Introduction to Blackpink:_
Blackpink is a 4-member female Korean pop band, consists of member Jisoo, Jennie, Rose and Lisa. This band debuted on 8th August 2016 under YG entertainment.

#### _This repository contains:_
  - File Structure of the initial setup
  - Dataset Outline
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
 
#### _References:_
Blackpink Profile: https://kprofiles.com/black-pink-members-profile/

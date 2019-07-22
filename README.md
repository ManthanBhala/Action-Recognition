# Sign Language Recognition

There is a need of a method or an application that can recognize sign language gestures so that the communication is possible even if someone does not understand sign language. With this work, we intend to take a basic step in bridging this communication gap using Sign Language Recognition..

* Industry: `Life Sciences`, `Public Sector`
* ML Domain: `Sequence Classification`, `Computer Vision`

## Problem Statement

A classification Model which takes less memory and account for gesture videos which contains sequence of images. Trained marker to distinguish performing action for streamline inference.
![GitHub Logo](/collateral/SIGN LANGUAGE RECOGNITION.jpg)

## Solution

Gesture videos are converted to sequence of frames which are human segmented. Embedddings are extracted from final pooling layer of MobileNetV2. These are passed to LSTM model which has fully connected layer in last. Classification is done using softmax.
![GitHub Logo](/collateral/architecture.jpg)

## Technology

* Keras 2.2.4

### ML Techniques

* CNN - For getting embeddings from frames
* LSTM - For sequence classification

### Programming languages

* Python 3.5.3 - For Machine Learning

### Infrastructure (training and Deployment)

* Google Compute Engine
    * n1-highmem-4 (4 vCPUs, 26 GB memory)
    * NVIDIA Tesla P100
* Google Cloud Console


## Setup
*    Download the repository

*    Convert video to frames
    
    [Video to Frame](/notebooks/video-to-frame_fps.py)
    
*    Augment the data.
    
    [Augmentation](/notebooks/data_aug.ipynb)
    
*    Apply human segmentation on the data.
    
    [Human Segmentation](/notebooks/human_segmentation.ipynb)

*    Run jupyter notebook
    
    * [Single Gesture Testing](/notebooks/single_gesture_testing.ipynb) for single gestures.
    * [Pipeline](/pipeline/pipeline.ipynb) for multiple gestures with marker.


## Training

* Extended Video Dataset (378 videos for 16 gestures used)
  * Training Dataset (train_videos)
  * Validation Dataset (val_videos)
  * Testing Dataset (test_videos)

*    Link to American Sign Language Lexicon Video Dataset - Used for training initially (Available open source)
    
    http://www.bu.edu/asllrp/av/dai-asllvd.html#download/
    
* Marker Dataset (13000 images used for each gesture and no-gesture)
  * Gesture images created from training dataset (gesture)
  * No-gesture images created from video gap between consecutive gestures (no_gesture)

## Testing Single Gesture
* Run [Train](/notebooks/train.ipynb) to see test results and plot confusion matrix as the following results.

![GitHub Logo](/collateral/confusion_matrix.png)

* Run [Single Gesture Testing](/notebooks/single_gesture_testing.ipynb) to see predicted outputs on videos as the following results.

![GitHub Logo](/collateral/single_gesture.gif)

![GitHub Logo](/collateral/single_gesture.png)

## Testing Multiple Gestures with marker

Run [Pipeline](/pipeline/pipeline.ipynb) to see following results.

![GitHub Logo](/collateral/results.png)

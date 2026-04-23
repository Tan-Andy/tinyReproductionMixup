# tinyReproductionMixup

This is the final code for TinyReproductions of the method Mixup

## Code Structure

The ```mixupProject.ipynb``` is the main notebook utilized for running the tinyreproduction and contains:

- All library imports which are publicly available and commonly utilized.
- ```train``` and ```test``` functions for ERM model and Mixup models
- Custom function called ```mixup``` which is the core Mixup Algorithim
- Custom function called ```mixupCriterion``` which is the custom loss function necessary for backpropogation
- Custom function called ```corruptLabels``` which is the method to corrupt labels for testing purposes.
- Code to run 1 epoch training and testing for either the ERM model or Mixup model
- Code to run training and testing of ERM model and Mixup models for multiple epochs with adjustable parameters
- Code to save multi-epoch tests to ```.csv``` files.
- Code to load ```.csv``` files for plot generation

NOTE: ```Assignment_03_Excercise.ipynb``` and ```.csv``` files are included for reference and are not necessary for running the training or testing of this tinyReproduction.

NOTE: A specified ```torch``` seed is utilized in the ```packages``` cell block; however, there may be small deviations from the provided results due to other packages.

## Dependencies

The written code requires these Python3 packages to run:

- ```torch```
- ```torchvision```
- ```numpy```
- ```matplotlib```
- ```pandas```

Additionally, Internet connection is required to download CIFAR-10 dataset and  Resnet-18 model from ```torchvision```. Download of dataset is embedded in notebook.

It is reccomended to run this notebook on Google Colab for maximum compatability

For saving CSV to google drive, the notebook must be ran in Google Colab and given drive access.

## Instructions to Run

In ```mixupProject.ipynb```, cell blocks that have a title ```(NECESSARY TO RUN)``` must be run sequentially from top to bottom. 

After that, here are individual steps for each test a user wants to take:

### Run Resnet 18 (ERM) for 1 Epoch

- Run all ```(NECESSARY TO RUN)```  blocks
- Run the block named ```Data loaders for CIFAR-10 No Corruption``` for training with no corruption OR run the block named ```Create Corrupted Train and test sets (NECESSARY TO RUN FOR CORRUPTION)(Corruption Val inside)``` for training with corruption. Edit the corruption value from 0 to 1. 20% is 0.2.
- Run the block ```Resnet 18 (ERM) 1 epoch

### Run Mixup for 1 Epoch

- Run all ```(NECESSARY TO RUN)```  blocks
- Run the block named ```Data loaders for CIFAR-10 No Corruption``` for training with no corruption OR run the block named ```Create Corrupted Train and test sets (NECESSARY TO RUN FOR CORRUPTION)(Corruption Val inside)``` for training with corruption. Edit the corruption value between 0 to 1. 20% corruption is 0.2.
- Run the block ```Mixup Test 1 epoch```
- Visualization of incorrect Predictions will be outputted

### Run Mixup and ERM for multiple Epochs

- Run all ```(NECESSARY TO RUN)```  blocks
- Run the block named ```Data loaders for CIFAR-10 No Corruption``` for training with no corruption OR run the block named ```Create Corrupted Train and test sets (NECESSARY TO RUN FOR CORRUPTION)(Corruption Val inside)``` for training with corruption. Edit the corruption value between 0 to 1. 20% corruption is 0.2.
- Run ```ERM and Mixup Setup for Data Collection (NECESSARY FOR MULTI EPOCH) (Shared Parameters Inside)``` to create identical models with your specified parameters. Find the comment ```# Share Parameter selection```
- Run ```Training ERM MULTI EPOCH``` and ```Training Mixup MULTI EPOCH```

### Export Comparison CSV

- Follow steps in instruction for "Run Mixup and ERM for multiple Epochs"
- Run ```Export Multi Epoch Comparison as CSV``` NOTE: Directory changes may need to be made to save outside of google drive or for different folders within google drive.

### Visualize Data

For cell blocks within the ```Visualize Data``` Header:

- Options to visualize are:

    - ```Visualize Test accuracy for single csv```
    - ```Visualize Test accuracy for multiple csv's```
    - ```Visualize Test loss for multiple csv's```

- Open desired corresponding cell block for desired visualization.
- Change variable ```fileName``` to the name of the csv file you want to visualize. You may need to change the extended directory path if files are not saved in the same spot.
- Run desired cell.

## Code Acknowledgement

Code within this notebook are either self-written by Andy or written & provided by the course from Assignment 3: CNN. Included in this repository is the submitted Assignment 3 submitted by Andy to the course for reference.

- The ```test``` and ```training``` functions for the ERM model are copied directly from the assignment 3 submission. These blocks were then modified for ```Mixup Train and Test Functions```.
- Loading of the CIFAR-10 dataset was copied from the assignment 3 submission.
- The custom functions within ```Mixup Custom Functions``` are uniquely written for this project by Andy.
- The viewing of the example provided by the Mixup paper was done for architecture understanding but no code was copied from the [source code](https://github.com/facebookresearch/mixup-cifar10/tree/main).
- The writing of the importation and exportation of CSV data was written by Andy.

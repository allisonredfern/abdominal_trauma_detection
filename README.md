# Abdominal Trauma Detection Using CNNs With and Without Organ Segmentation
## BMSC-GA 4493 / BMIN-GA 3007 Deep Learning in Medicine Final Project

Traumatic injuries are a leading cause of death among young people, often resulting in abdominal injury. Rapid and accurate detection of injuries from medical imaging is crucial for patient care. This project employs Convolutional Neural Networks (CNNs) to detect liver injury from 3D abdominal CT scans, investigating the impact of organ segmentation on injury detection. The segmentation model, a 3D U-Net, performs pixel-level classification of liver or non-liver in each 3D scan. Predicted segmentations are used to create cropped 3D liver scans for each patient. Both cropped and uncropped images are utilized to train two classification model types: a 2D ResNet18 \& LSTM model and a 3D ResNet18 model. The models trained on cropped images outperform those trained on uncropped images due to the reduction of noise and improved focus on the liver region.

Below are each folder in the repo.  First the raw segmentations and images must be downloaded from Kaggle by running `kaggle competitions download -c rsna-2023-abdominal-trauma-detection` in command line.  Paths to this data may need to be updated throughout the code to reproduce results.  After downloading the data, run `data_preprocessing.ipynb`.  Then train the segmentation model and mask images using `segmentation_model.ipynb`.  Finally each classification model can be run in parallel and their final evaluation is done in `classification_model_eval.ipynb`.

## EDA
- `EDA.ipynb` - contains exploratory data analysis of raw data

## data
- `data_preprocessing.ipynb` - data preprocessing for segmentations, CT scans, and metadata as described in report  
- 'CSV files' - preprocessed metadata in train/val/test splits

## models
- `segmentation_model.ipynb` - 3D U-Net segmentation model architecture, training, and evaluation as well as code to mask all training images for classification models
- `classification_model_2d_resnet_LSTM_cropped.ipynb` - 2D ResNet \& LSTM architecture, as described in report, trained on cropped images of the liver
- `classification_model_2d_resnet_LSTM_uncropped.ipynb` -  2D ResNet \& LSTM architecture, as described in report, trained on uncropped images of the liver
- `classification_model_3d_resnet_cropped.ipynb` - 3D ResNet architecture, as described in report, trained on cropped images of the liver
- `classification_model_3d_resnet_uncropped.ipynb` - 3D ResNet architecture, as described in report, trained on uncropped images of the liver
- 'Pickle Files' - Loss and accuracy outputs per epoch for each model

## evaluation 
- `classification_model_eval.ipynb` - evaluation and comparison of the 4 liver injury detection models, including an assessment on model explainability
- 'Pickle Files' - list of dataframes of results for each model type

# Abdominal Trauma Detection Using CNNs With and Without Organ Segmentation
## BMSC-GA 4493 / BMIN-GA 3007 Deep Learning in Medicine Final Project

**Abstract:** (Abstract here)

## EDA
- `EDA.ipynb` - contains exploratory data analysis of raw data

## data
- `data_preprocessing.ipynb` - data preprocessing for segmentations, CT scans, and metadata as described in report  
  To download raw Kaggle data, run `kaggle competitions download -c rsna-2023-abdominal-trauma-detection` in command line
- 'CSV files' - preprocessed metadata in train/val/test splits

## models
- `segmentation_model.ipynb` - 3D U-Net segmentation model architecture, training, and evaluation
- `classification_model_2d_resnet_LSTM_cropped.ipynb` - 2D ResNet \& LSTM architecture, as described in report, trained on cropped images of the liver
- `classification_model_2d_resnet_LSTM_uncropped.ipynb` -  2D ResNet \& LSTM architecture, as described in report, trained on uncropped images of the liver
- `classification_model_3d_resnet_cropped.ipynb` - 3D ResNet architecture, as described in report, trained on cropped images of the liver
- `classification_model_3d_resnet_uncropped.ipynb` - 3D ResNet architecture, as described in report, trained on uncropped images of the liver
- 'Pickle Files' - Loss and accuracy outputs per epoch for each model

## evaluation 
-`classification_model_eval.ipynb` - evaluation and comparison of the 4 liver injury detection models, including an assessment on model explainability
- 'Pickle Files' - list of dataframes of results for each model type

SIIM-ISIC Melanoma Classification
https://www.kaggle.com/c/siim-isic-melanoma-classification

Problem: Computer Vision (Binary Classification)

Data files are too big to be added here, please see kaggle link

###### Used these datasets for training (courtesy of https://www.kaggle.com/cdeotte) - 
https://www.kaggle.com/cdeotte/melanoma-128x128
https://www.kaggle.com/cdeotte/melanoma-192x192
https://www.kaggle.com/cdeotte/melanoma-256x256
https://www.kaggle.com/cdeotte/melanoma-384x384
https://www.kaggle.com/cdeotte/melanoma-512x512
https://www.kaggle.com/cdeotte/melanoma-768x768


###### External (old ISIC competition data - 2019/2018/2017)
https://www.kaggle.com/cdeotte/isic2019-128x128
https://www.kaggle.com/cdeotte/isic2019-192x192
https://www.kaggle.com/cdeotte/isic2019-256x256
https://www.kaggle.com/cdeotte/isic2019-384x384
https://www.kaggle.com/cdeotte/isic2019-512x512
https://www.kaggle.com/cdeotte/isic2019-768x768


This might be deleted by Kaggle user, so here is a link how to create these images - 
https://www.kaggle.com/c/siim-isic-melanoma-classification/discussion/165526
https://www.kaggle.com/cdeotte/how-to-create-tfrecords


###### Used this baseline(courtesy of https://www.kaggle.com/cdeotte) for my experiments -
https://www.kaggle.com/cdeotte/triple-stratified-kfold-with-tfrecords

Train_Inf_B2-256.ipynb - Training and inference code for 1 single model (Different experiements ran on same notebook by changing parameters)

GBT.ipynb - Trained gradient boosted trees and xgb classifier on meta-data

CV_results.xlsx - Cross Validated results for all experiments

###### Final Ensemble Model

**Sr. No. -Size -Model -OOF_AUC -Public LB -Private LB -Weight**

1 -192 -B6 -0.906 -0.9323 -0.9218 -2

2 -256 -B7 -0.908 -0.9339 -0.9246 -4

3 -384 -B6 -0.914 -0.9434 -0.9255 -5

4 -512 -B6 -0.909 -0.9499 -0.9205 -4

5 -768 -B6 -0.918 -0.9493 -0.9285 -5

Image Ensemble - Random searched the weights for max OOF_AUC.
OOF_AUC - 0.9394 Pub. LB - 0.9528 Pri. LB - 0.9370

Gradient Boosted Trees (5 fold CV) with 3 features only (age, sex, location)
OOF_AUC - 0.68 Pub. LB - 0.6777 Pri. LB - 0.6639

Final ensemble (0.87 * image ensemble + 0.13 * Gradient Boosted Tree Model) [Experimented with weights]
OOF_AUC - 0.9382 Pub. LB - 0.9548 and 72/3319, Silver medal - Top 3% on private LB


Important Links for later reference - 
https://www.kaggle.com/c/siim-isic-melanoma-classification/discussion/175614
https://www.kaggle.com/cdeotte/forward-selection-oof-ensemble-0-942-private

The PANDA challenge for Prostate Cancer detection (ISUP grade) 
https://www.kaggle.com/c/prostate-cancer-grade-assessment

Problem: Computer Vision (multi class classification)

Data files are too big to be added here, please see kaggle link
Used this dataset for training - https://www.kaggle.com/raghaw/panda-dataset-medium-25-256-256

This might be deleted by Kaggle user, so here is a link how to create these images - https://www.kaggle.com/c/prostate-cancer-grade-assessment/discussion/161500

The whole slide images (tiff files) are too big to feed into a CNN, so the idea is to cut relevant tiles from these images and then use them as input.
Idea courtesy - https://www.kaggle.com/iafoss/panda-16x128x128-tiles

I tried various tile sizes from different image resolutions. The maximum tile size I could work with was 256 x 256 (medium resolution) 
and using 25 such tiles combined into 1 image. **It achieved a public leaderboard score of 0.81900 and private leaderboard score of 0.83407**

Panda_training_256_25.ipynb - Training code, used train on batch because whole data cannot be fit to memory in kaggle notebook 
Learning rate set manually (got this from cosine decay by training on a small subset of data)

Panda_inference_256_25.ipynb - Inference code

Most high score kernels on kaggle (>0.89) have used 36 tiles of 256 x 256, but mostly all of them have used private hardware to train those models.
It is not possible to fit the data in a kaggle notebook hardware. [Max batch size achievable was 2 which was not leading to convergence]

# Pose_Estimation
The matlab code pose/demo.m estimates the pose of uppper part of Human body used with [caffe-heatmap regressor](https://github.com/tpfister/caffe-heatmap). This code uses FLIC pretrained model - [Fusion model trained on FLIC](http://tomas.pfister.fi/models/caffe-heatmap-flic.caffemodel). 
# Testing instructions
Put the pretrained model in caffe-heatmap/models and run the matlab file pose/demo.m. Instructions for training your own model are provided at [caffe-heat](https://github.com/tpfister/caffe-heatmap).

# Personalization
This uses the temporal informatioin video to improve the model.

## Prerequsites
matlab, VLFeat, DeepFlow.

## Running 

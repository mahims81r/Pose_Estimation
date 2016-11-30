# Pose_Estimation
The matlab code pose/demo.m estimates the pose of uppper part of Human body used with [caffe-heatmap regressor](https://github.com/tpfister/caffe-heatmap). This code uses FLIC pretrained model - [Fusion model trained on FLIC](http://tomas.pfister.fi/models/caffe-heatmap-flic.caffemodel). 
### Testing instructions
Put the pretrained model in caffe-heatmap/models and run the matlab file pose/demo.m. Instructions for training your own model are provided at [caffe-heat](https://github.com/tpfister/caffe-heatmap).

# Personalization
This uses the temporal informatioin video to improve the model.

## Prerequsites
matlab, VLFeat, DeepFlow.

## Running on your own video
 - Resize the video so that the person has shoulder width approx. 100px wide. Put the video in videos and add it to path.
 - First set path in options then Compute the dense optical flow - collect_optic_flow('myvideo','youtube');
 - produce the initial annotations and save them to matlab structure - save('./demo_data/initialisation/myvideo.mat','detections');
 - propagate the initial poses - detections = propagate('myvideo','youtube', './demo_data/initialisation/myvideo.mat',1,1,1);
 
### Finally pose output is visualized with-
 - show_skeleton('./demo_data/videos/myvideo.avi', 1,detections.manual.frameids,detections.manual.locs,0);
 
### Fine tuning the caffe-model of ConvNets-
 - First of all set the all of the paths in  ./options/propagation_options_youtube.m acc. to your directory structure.
 - Run the demo.m by setting the isFineTune to true in demo.m.
 - Finally to start the finetunig you need to run the train.sh script generated after running demo.m
 
## References
[1] J. Charles, T. Pfister, D. Magee, D. Hogg and A. Zisserman "[Personalized human video pose estimation](http://arxiv.org/abs/1511.06676)", CVPR 2016.

[2]  T. Pfister J. Charles  and A. Zisserman "[Flowing ConvNets for Human Pose Estimation in Videos](http://arxiv.org/abs/1506.02897)", ICCV 2015.

# Wheat_head_prediction
Wheat Head Count using Computer Vision and Deep Learning


Problem Definition:
Wheat Head Count using Computer Vision 


![alt text](https://github.com/Deepika-Sharma08/Wheat_head_prediction/blob/master/supporting_images/Wheat.png?raw=true)





















Applications: 
1. Crop health monitoring using Computer vision and Deep Learning.
2. Yield approximation using Computer vision and Deep Learning.


Challenges: 
1. Wheat heads are hard patterns to detect because of their size and overlapping heads.
2. Appearances vary due to maturity, color, genotype and head orientation.
3. Wind can blur the images.


Solution Approach:
Using Image Processing, Image Segmentation and Deep learning Model VGGNet.

Prerequisite:
1. TensorFlow 2.2 CPU/GPU (any)
2. Opencv 4.2
3. Scipy >= 1.4
4. Keras >= 2.1 (This will get installed when TensorFlow is installed, there is no need to install it separately, however keeping a check on version is required)
5. VGG19 pre trained model (Download it form internet)


Specifics:
1. Input image RGB size: 512*512 (3000 images)
2. Annotated images for training.
3. Non annotated images for testing (~380 images)



![alt text](https://github.com/Deepika-Sharma08/Wheat_head_prediction/blob/master/supporting_images/Input%20and%20Annotated.png?raw=true)













Solution Steps:
1. (most imp!) Pre-processing on input images such that algorithm machine learns background vs foreground patterns. (only two classes 1. background, 2. wheat heads)

2. Training VGG model with n_class = 2, as solution is only to detect wheat head and rest is background.
3. Input images for training are actual RGB images.
4. Annotated images contain only two classes background and wheat heads (based on segmentation provided) for training. Path to annotated images folder is provided to model for training.
5. Hyper parameter tuning to find right num_of_epochs, steps_per_epoch. Apparently, shallow training worked out better.

6. Achieved accuracy 70% [This accuracy indicates, model was able to detect wheat heads approximately 70% times]
7. Model testing using test data set.

8. Validate accuracy on test data. Accuracy criteria: 
8.1 co-ordinates match between annotated segments vs model predicted segments in test images.
8.2 Number of segments in annotated images vs number of segments predicted by model (cut off 70%).



Results:
![alt text](https://github.com/Deepika-Sharma08/Wheat_head_prediction/blob/master/output_1.png?raw=true)


![alt text](https://github.com/Deepika-Sharma08/Wheat_head_prediction/blob/master/output_2.png?raw=true)
















Caveats:
1. Present model works fine for images where color map is consistent.
2. Darker images where foreground and background are getting mixed and algorithm is unable to separate the two.
![alt text](https://github.com/Deepika-Sharma08/Wheat_head_prediction/blob/master/Caveats.png?raw=true)









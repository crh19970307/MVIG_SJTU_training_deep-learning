#MVIG_SJTU_training_deep-learning

##Environment setting

I have installed ubuntu 16.04 LTS in my computer with NVIDIA graphic card. I have installed caffe, tensorflow and torch in my computer successfully. There are many problems when installing caffe so I spend a few days. I have also installed CUDA8.0, CUDNN v3, OpenCV3.0.

##Course CS231n

This course is a deep dive into details of the deep learning architectures with a focus on learning end-to-end models for tasks such as image classification, localization and detection, particularly image classification.
I find videos on the youtube. The page of cs231n in cs231n.github.io has been removed but I found another page with notes and assignments. A group in Zhihu has translated the course into Chinese so that I can understand the course more easily.


##Five topics
###Object Detection
####[Faster RCNN](https://github.com/rbgirshick/py-faster-rcnn)
The idea of faster RCNN is from RCNN and fast RCNN as the figure shows.

![image](https://camo.githubusercontent.com/60e17201986ba4655487199ce370292a0820e2da/687474703a2f2f696d672e626c6f672e6373646e2e6e65742f3230313630343134313634353336303239)

Faster R-CNN, is composed of two modules. The first module is a deep fully convolutional network that proposes regions, and the second module is the Fast R-CNN detector that uses the proposed regions.

The process of training consists of 4 steps.

1.Train the RPN.

2.Train a separate detection network by Fast R-CNN

3.Use the detector network to initialize RPN training, but fix the shared convolutional layers and only fine-tune the layers unique to RPN.

4.Keeping the shared convolutional layers fixed, fine-tune the unique layers of Fast R-CNN.

####[Yolo9000](http://pjreddie.com/darknet/yolo/)
Better Faster Stronger

YOLO9000 is a real-time framework for detection more than 9000 object categories by jointly optimizing detection and classification. We use WordTree to combine data from various sources and our joint optimization technique to train simultaneously on ImageNet and COCO. YOLO9000 is a strong step towards closing the dataset size gap between detection and classification.
###Pose Estimation
####[RMPE](https://cvsjtu.wordpress.com/rmpe-regional-multi-person-pose-estimation/)
![image](/src/1612.bmp)

 Different from traditional training method, we train the SSTN+SPPE module with images generated by deep proposals generator (DPG).
 
 The architecture of Deep Proposals Generator.
 ![image](/src/234.bmp)
 
####[Cao et al](https://github.com/ZheC/Realtime_Multi-Person_Pose_Estimation)

###Multi-object tracking
####[Learn to track](https://github.com/yuxng/MDP_Tracking)
###Object Segmentation
####[Instance-aware](https://github.com/daijifeng001/MNC)
![image](/src/111.jpg)

Multi-task Network Cascades for instance-aware semantic segmentation. At the top right corner is a simplified illustration.

In our MNC model, the network takes an image of arbitrary size as the input, and outputs instance-aware semantic segmentation results. The cascade has three stages: proposing box-level instances, regressing mask-level instances, and categorizing each instance.

###Scene Parsing
####[Pyramid-Parsing](https://github.com/hszhao/PSPNet)

##Hourglass Model
Architecture of hourglass model
![image](/src/234567.jpg)

An illustration of a single hourglass module. Each box in the gure corresponds to a residual network block. The number of features is consistent across the whole hourglass.

The design of the hourglass is motivated by the need to capture information at every scale. The hourglass is a simple, minimal design that has the capacity to capture all of these features and bring them together to output pixel-wise predictions.

The hourglass is set up as follows: Convolutional and max pooling layers are used to process features down to a very low resolution. At each max pooling step, the network branches off and applies more convolutions at the original pre-pooled resolution. After reaching the lowest resolution, the network begins the top-down sequence of upsampling and combination of features across scales. After reaching the output resolution of the network, two consecutive rounds of 1x1 convolutions are applied to produce the final network predictions. 


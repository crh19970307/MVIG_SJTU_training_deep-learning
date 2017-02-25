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
###Pose Estimation
####[RMPE](https://cvsjtu.wordpress.com/rmpe-regional-multi-person-pose-estimation/)
####[Cao et al](https://github.com/ZheC/Realtime_Multi-Person_Pose_Estimation)
###Multi-object tracking
####[Learn to track](https://github.com/yuxng/MDP_Tracking)
###Object Segmentation
####[Instance-aware](https://github.com/daijifeng001/MNC)
###Scene Parsing
####[Pyramid-Parsing](https://github.com/hszhao/PSPNet)

##Hourglass Model

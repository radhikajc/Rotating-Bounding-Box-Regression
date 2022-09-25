# Rotating-Bounding-Box-Regression


A data synthesizer generates images and labels. The goal is to train a model with at most 4.5 million trainable parameters which determine whether each image has a star and, if so, find a rotated bounding box that bounds the star.
More precisely, the labels contain the following five numbers, which your model should predict:
• the x and y coordinates of the center
• yaw
• width and height. 
• If there is no star, the label consists of 5 np.nans. The height of the star is always noticeably larger than its width, and the yaw points in one of the height directions. The yaw is always in the interval [0, 2 * pi), oriented counter-clockwise and with zero corresponding to the upward direction.

Steps:
1. Implemented network for rotated object detection using modulated Rotation Loss. 
2. 2. To implement the network, used ResNet18 with classification and regression heads.
3. Introduced normalized and unnormalized functions with a range of labels as [0,1]. 
4. 4. Classified image with a label based on values of the generated label.

<img width="873" alt="image" src="https://user-images.githubusercontent.com/103969912/192167380-da920043-74c2-4bfc-938b-8ada5a35c260.png">



Evaluation:
1. Loss function bridges the discontinuity in the values of yaw.
2. ET taken by training model: 126 Minutes
3. Final Score:
IOU: 0.5809 Score: 0.247

<img width="517" alt="image" src="https://user-images.githubusercontent.com/103969912/192167323-948d72f6-2166-4fa1-9d55-862717585ff0.png">


Citations:
1. Loss Function: https://github.com/facebookresearch/detectron2
2. Train model: https://pyimagesearch.com/2021/07/19/pytorch-training-your-first-convolutional-neural- network-cnn/
3. Network : https://github.com/kevinghst/spaceship_submit/blob/master/network.py

# MultiPerson_Pose_Estimator
An Implementation And Evaluation of Multi-Person Pose Estimation Using Deep Learning (Movenet) 

METHODOLOGY

The methodology underlying MoveNet is rooted in a combination of architectural choices and innovative strategies that collectively enable accurate and real-time human pose estimation. At the heart of this methodology lies the adoption of the EfficientNet backbone, which serves as the foundation for the network's design. The EfficientNet backbone is renowned for its ability to strike an optimal balance between model complexity and accuracy by judiciously scaling the depth, width, and resolution of the network. This foundational element provides MoveNet with a solid starting point for efficient yet accurate pose estimation.

One of the pivotal techniques employed within MoveNet is the integration of depthwise separable convolutions. These convolutions, consisting of a depthwise convolution followed by a pointwise convolution, efficiently capture spatial and channel-wise correlations in the data. By doing so, they substantially reduce the computational demands traditionally associated with regular convolutions. This technique is pivotal in ensuring that MoveNet maintains its efficiency, making it suitable for real-time applications where computational resources are constrained.

A key component of MoveNet's methodology is its prediction of keypoint heatmaps. These heatmaps act as probability maps, indicating the likelihood of keypoints being present at various spatial locations. By generating these heatmaps for different body parts, MoveNet gains the ability to accurately pinpoint the locations of key body keypoints within images, forming the basis for subsequent pose estimation. 

An innovative aspect of MoveNet's methodology is its capability to perform both single-person and multi-person pose estimation. In the context of multi-person estimation, MoveNet produces a unified set of keypoints and heatmaps that capture the poses of all individuals present within an image. This approach simplifies the process of estimating poses for multiple people, enhancing efficiency without sacrificing accuracy.

In addition, MoveNet incorporates a pose refinement module that fine-tunes keypoint predictions based on the heatmaps generated. This step further enhances the accuracy of pose estimation, ensuring that the final output is precise and aligned with the actual human poses within the images.

In essence, the methodology of MoveNet revolves around a judicious fusion of architectural elements like the EfficientNet backbone, depthwise separable convolutions, and heatmap-based predictions. These components collectively form a powerful framework that not only maintains computational efficiency but also achieves remarkable accuracy in real-time human pose estimation tasks.

IMPLEMENTATION

The provided code snippet exemplifies the practical implementation of the MoveNet model for multi-person pose estimation using TensorFlow and OpenCV. It is designed to process a video source, capturing individual frames, detecting multiple human subjects within each frame, and subsequently estimating their respective body keypoints. The implementation begins by loading the MoveNet model through TensorFlow Hub, utilizing the 'serving_default' signature to enable inference. Key functions for rendering keypoints and connecting lines between them are defined to visually depict the estimated poses.

Within the core processing loop, each frame undergoes several stages. Firstly, the frame is resized using TensorFlow's image manipulation capabilities to ensure uniformity in input dimensions to the model. Subsequently, the MoveNet model is employed for inference, predicting keypoints and associated scores for each individual detected in the frame. The derived keypoints and scores are then utilized in the rendering functions to overlay visual representations of body keypoints and connecting lines on the frame. The modified frame, now enhanced with pose information, is displayed using OpenCV's display functions.

The processing loop continues until the video concludes or is manually terminated by pressing the 'q' key. By marrying the capabilities of TensorFlow for deep learning and OpenCV for image manipulation and visualization, this code exemplifies the dynamic application of the MoveNet model to real-time video data, allowing for the visualization of estimated multi-person human poses within the video stream.

RESULT IMAGES
<img width="180" alt="image" src="https://github.com/PurvajaNarayan/MultiPerson_Pose_Estimator/assets/154343922/f227ad5a-b65c-40be-acb8-54bd07ec057e">

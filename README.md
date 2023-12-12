# AM-SegNet
In this work, we propose a novel lightweight neural network, AM-SegNet, to perform semantic segmentation and feature quantification on X-ray images collected from various AM (advanced manufacturing) beamtime experiments. For the comprehensive training and testing of CNN models, we have established a large-scale benchmark database comprising more than 10,000 pixel-labelled X-ray images. Experimental results indicate that AM-SegNet outperforms other available CNN-based segmentation models in different aspects, i.e., accuracy, speed and robustness. The well-trained AM-SegNet has been adopted to expedite the quantification of critical features and conduct correlation analysis. The accuracy and efficiency of AM-SegNet are further validated in types of AM, and for other advanced manufacturing techniques, making it closer to achieving real-time segmentation and quantification of X-ray images in high-speed synchrotron experiments.


## Lightweight convolution block 
The lightweight convolution block begins with a squeeze convolution layer (1x1 kernels) that limits the number of input channels, denoted as n1, to be processed by the following expand module. The expand module includes: (1) separable convolutions; (2) residual convolution with 1x1 kernels; and (3) expand convolution with 3x3 kernels. Specifically, separable convolution decomposes a regular convolution operation into two separate steps: depth-wise convolution and point-wise convolution. Depth-wise convolution applies a single filter to individual input channels, bringing about a feature map for each input channel separately. All the resulting feature maps are concatenated into a single output tensor and processed by the following point-wise convolution with 1x1 filters. Three sets of outputs from the expand layer are concatenated in the concatenation layer, increasing the channel number from n1 to 4xn1. The capability and efficiency of such squeeze-expand operations has been successful validated in the task of image classification and defect detection. Additionally, in the last encoder step, standard convolutional layers are retained in order to ensure the model’s robustness and generalisation and mitigate over-fitting problems. 

## Attention mechanism
For better model sensitivity and higher segmentation accuracy, the attention mechanism has been introduced to deep neural networks. It has been found that attention gates can help to disambiguate irrelevant and noisy responses and update the model parameters based on spatial regions that are more relevant to the given task. Inspired by this, a customised attention gate is proposed in this study. The purpose is to highlight the salient features in the last encoding stage, without consuming excessive computation resources. 

## Version information
- Python: 3.9.16
- tensorflow: 2.10.1
- keras: 2.10.0
- ipykernel: 6.15.0
- numpy: 1.25.0
- pandas: 2.0.3

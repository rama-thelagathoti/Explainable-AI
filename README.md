# Explainable Machine Learning using GRAD-CAM & Saliency map 
Introduction

Explainable machine learning is the method of interpreting the decisions made by a complex deep learning model. With the latest advancements in Artificial Intelligence, there are millions of pretrained machine learning models which are complex with millions of parameters, yet they provide accurate decisions.  However, it is crucial to comprehend the reason behind a decision made by such model. This knowledge helps the end user to trust the model at the same time several critical information will be revealed. For instance, a model trained to predict the onset of diabetes may be trustworthy and interpretable provided if the user knows why the model predicted it as diabetes.  Because a user who may be predicted as diabetes wants to know reasons behind the prediction so that he can take preventive measures. In such scenarios interpretable models plays a vital role.

GRAD-CAM (Gradient-weighted Class Activation Mapping)

Zhou et al. in the year of 2016 introduced the concept of Class Activation Map (CAM). In this approach, the authors have replaced the fully connected layer with Global Average Pooling, at the end of the neural network. Then the average of all the feature maps are concatenated to a vector that will be given as an input to softmax layer. This method facilitates the programmers and end users to understand the important features behind the final prediction. GRAD-CAM is a more versatile variant of CAM, which was introduced by Selvaraj et al., that produces the heatmap of input image by computing the gradient. The gradient is computed to generate heatmap at the convolutional layer rather than at dense neural layer level.  

Saliency maps

Saliency maps are one way to visualize the interpretability of the deep learning model. It was first introduced by Simonyan and colleagues in the paper titles “Deep inside convolutional networks: Visualizing image classification models and saliency maps”. Saliency maps computes the effect of each pixel on the final prediction then generates a map that describes the important pixel that have influenced the prediction. 

Output analysis

![Picture6](https://user-images.githubusercontent.com/36952323/217413481-d998c735-cad0-434a-818a-a012be5cad83.png)

Input images are depicted as follows

![Picture7](https://user-images.githubusercontent.com/36952323/217413588-348bd875-39a1-4e1c-97e8-e99eb30748b1.png)

Following steps summarizes the methodology 
1.	Load pretrained VGG model
2.	Load the images
3.	Prepare images suitable to be used as input for pretrained VGG network
4.	Display top 5 classes for each input that the model predicted 
5.	To measure the gradient of the output softmax layer will be replaced with linear layer 
6.	Finally, saliency map and GradCAM are computed. 

Saliency map output

![Picture8](https://user-images.githubusercontent.com/36952323/217413659-239d40b1-6c26-49cf-b8c1-0ebd8f1ae5dc.png)

Grad-CAM output

![Picture9](https://user-images.githubusercontent.com/36952323/217413735-8e203439-561d-45aa-9c65-828e0ced18e9.png)


The saliency map computes the influence of every pixel on the final model prediction whereas Grad-CAM grad measures the gradient of output with respect to the feature map of the layer before SoftMax. 
In the above example, according to saliency map output, prediction of cat is highly influenced by the pixels around the head. As per Grad-CAM, outcome is predicted because of the features around head as well as the right leg posed in the front side. similarly, for dog and hen, both methods produced head as the most effective feature.  For tiger, head and right leg seems to be best predictors that influenced the final decision. 

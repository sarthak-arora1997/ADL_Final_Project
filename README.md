# ADL_Final_Project
Detecting Cancer Metastases on Gigapixel Pathology Images 

## Applied Deep Learning Final Project (Fall 2022)
Authors: Sarthak Arora, Ridwan Olawin

### Objective

Metastasis detection is currently performed by pathologists by examining large expansions of biological issues. This is a very labor intensive and error prone process and only skilled pathologists are able to make accurate predictions. Our objective is to follow the stratergy in this [paper](https://arxiv.org/pdf/1703.02442.pdf) and utilize the power of Deep Learning to train a model which can help us locate the cancerous pixels in these large images.

### Data Set
We get the raw data from the Gigapixel Pathology Images, each has a tumor slide and a corresponding mask from [The CAMELYON16](https://camelyon16.grand-challenge.org/Data/) challenge. In the training dataset we have 4000 patches of size 299X299 (2000 from Zoom Level 1 and 2000 from Zoom Level 2) which have been sampled from these images at a high magnification level. In the validation set we have similar 1000 patches (500 each from the 2 zoom level). For testing we use two slides. Due to limitation in computational power we could not work with large datasets (You can easily generate 10,000 patches at the higher zoom levels i.e. level 0,1 or 2 each). 

### Modeling
We have used pre-trained weights from the InceptionV3 model. We freeze up 100 layers and fine tune the others. Also added a Global Average Pooling layer to make the training process faster by reducing the number of trainable parameters. To reduce overfitting we have added a drop out layer as well. We create two exactly similar models, one for each zoom level. 

Model Plot             |  Model Summary
:-------------------------:|:-------------------------:
![alt text](https://github.com/sarthak-arora1997/ADL_Final_Project/blob/main/model_plot.png?raw=true)  |  ![alt text](https://github.com/sarthak-arora1997/ADL_Final_Project/blob/main/model_summary.png?raw=true)




### Results
On evaluating the model on the test set we created by the sliding window approach on 2 slides we get the following results:
* Model1 (trained at zoom level 4) gives a 78.51% of test accuracy
* Model2 (trained at zoom level 3) gives a 91.84% of test accuracy

**NOTE: such high test accuracy is because of the fact that the test set is very small and does not have a lot of cancerous cells present in it. It is not indicative of how the model would perform in the real world.**

We also created a mask using our models trained above and below we can see the original mask and prediction mask both overlayed on the same slide to comapre how they look. 

Original            |  Predicted
:-------------------------:|:-------------------------:
![alt text](https://github.com/sarthak-arora1997/ADL_Final_Project/blob/main/original_mask.png?raw=true)   |  ![alt text](https://github.com/sarthak-arora1997/ADL_Final_Project/blob/main/predicted_mask.png?raw=true) 



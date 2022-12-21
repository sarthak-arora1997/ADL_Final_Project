# ADL_Final_Project
Detecting Cancer Metastases on Gigapixel Pathology Images 

## Applied Deep Learning Final Project (Fall 2022)
Authors: Sarthak Arora, Ridwan Olawin

### Objective

Metastasis detection is currently performed by pathologists by examining large expansions of biological issues. This is a very labor intensive and error prone process and only skilled pathologists are able to make accurate predictions. Our objective is to follow the stratergy in this [paper](https://arxiv.org/pdf/1703.02442.pdf) and utilize the power of Deep Learning to train a model which can help us locate the cancerous pixels in these large images.

### Data Set
We get the raw data from the Gigapixel Pathology Images, each has a tumor slide and a corresponding mask from [The CAMELYON16](https://arxiv.org/pdf/1703.02442.pdf) challenge. In the training dataset we have 4000 patches of size 299X299 (2000 from Zoom Level 1 and 2000 from Zoom Level 2) which have been sampled from these images at a high magnification level. In the validation set we have similar 1000 patches (500 each from the 2 zoom level). For testing we use two slides. Due to limitation in computational power we could not work with large datasets (You can easily generate 10,000 patches at the higher zoom levels i.e. level 0,1 or 2 each). 



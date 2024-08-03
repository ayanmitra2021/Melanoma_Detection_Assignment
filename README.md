# Melanoma_Detection_Assignment
The project  build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Acknowledgements](#acknowledgements)

## General Information
This project written and executed on Google Colab with T4 GPU uses over 2000 images obtained from the  https://drive.google.com/uc?id=1xLfSQUGDl8ezNNbUkpuHOYvSpTyxVhCs. 
- In order to prepare the dataset, the impages are first downloaded in the content folder and then extracted under a "Melanoma" subfolder. The training and validation dataset was split between 80% and 20% respectively using keras.preprocessing library.  
- Next a sequential CNN is created with 2 layers, 1 flatten layer, and a final softmax layer. 
- ReLU is used for activation, and Batch Normalization is used in each layer. 
- Also DropOut is used in each layer with 25% value
The model was compiled with categorical cross entropy. With the GPU's horse power, the model was trained with 20 epochs under 130 seconds. 
However, based on resulting training and validation accuracy/loss plots, it seems like the model might be "underfitted" the data. One of the key reason for this was found to be class imbalance. For example it was noted, the number of samples in each class is as follows:
1. pigmented benign keratosis: 20.63%
2. melanoma: 19.56%
3. basal cell carcinoma: 16.79%
4. nevus: 15.94%
5. squamous cell carcinoma: 8.08%
6. vascular lesion: 6.21%
7. actinic keratosis: 5.09%
8. dermatofibroma: 4.24%
9. seborrheic keratosis: 3.44%

In order to address this class imbalance issue, the Augmentor library was used to add more images. This helped to increase the training dataset from 2239 to 6739. 
Next after this when the same model (described above) was used to train the model, the underfitting problem was eliminated. 

## Technologies Used
- pandas
- numpy
- matplotlib.pyplot
- keras
- tensorflow

## Acknowledgements
Give credit here.
- https://wikipedia.org
- https://stats.stackexchange.com/
- https://math.stackexchange.com/

## Contact
Created by [@ayanmitra2021] - feel free to contact me!
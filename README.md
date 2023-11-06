# Brain_tumor_classification_MRI

### Introduction
A Brain tumor is considered as one of the aggressive diseases, among children and adults. Brain tumors account for 85 to 90 percent of all primary Central Nervous System(CNS) tumors. 
Every year, around 12,000 people are diagnosed with a brain tumor. The 5-year survival rate for people with a cancerous brain or CNS tumor is approximately 34 percent for men and36 percent for women. 
Brain Tumors are classified as: Benign Tumor, Malignant Tumor, Pituitary Tumor, etc. Proper treatment, planning, and accurate diagnostics should be implemented to improve the life expectancy of the patients. 
The best technique to detect brain tumors is Magnetic Resonance Imaging (MRI). A huge amount of image data is generated through the scans. These images are examined by the radiologist.
A manual examination can be error-prone due to the level of complexities involved in brain tumors and their properties.

### Objective
According to the World Health Organization (WHO), proper brain tumor diagnosis involves detection, brain tumor location identification, and classification of the tumor on the basis of malignancy, grade, and type.
Based on the convolutional neural network (CN), we can help doctors identify a brain tumor based on the results of Magnetic Resonance Imaging (MRI).

### Dataset
The type of tumor is determined by the cells forming it (histological classification).The most common types of brain cancer - 4 classes:

                                                                                       1. Not tumor: indicates that those images do not contain a tumor.
                                                                                       2. Meningioma: is a type of tumor that develops from the membranes that surround the brain and spinal cord.
                                                                                       3. Glioma: is a type of tumor that develops from glial cells, which are cells that support and protect neurons.
                                                                                       4. Pituitary tumor: is a type of tumor that develops from the pituitary gland, which is located at the base of the brain.
I have chosen 3 models to train the neural networks: ResNet50 architecture,
                                                     VGG16,
                                                     Xception. 


### Conclusion
I unfroze the last 20 layers of ResNet50 and searched for optimal hyperparameters. 

1. ResNet50 model shows the best and stable results.
The results are above 90%.  But with one hidden layer the model confuses glioma with meningioma, gives 0.65%, in other cases 100%. 
Best performance was given with two hidden layers. accuracy training 99%, test 96% and no errors. 
The best hyperparameters for transfer learning on ResNet50 in our project were:

     2 dense layers.
     GlobalAveragePooling2D
     Adam optimizer
    callbacks: early stopping and reduced learning rate
    dropout, flatten/
2. VGG16 -  Working with the Architecture of model VGG16 , I use all 16 layers and choose the optimal hyperparameters. 
The VGG16 model shows stable and moderate results above 85%: 
But it gives an error for glioma and meningioma in all cases. 
The best and stable results are shown by the model with one layer.
3. Xception - If we compare all three attempts, the model with 1 convolutional layer and 2 hidden layers shows more or less stable results. 

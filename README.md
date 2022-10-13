# Covid-19 Predicition

The project includes the prediction that whether a patient is covid +ve or not based on his/her chest radiography images. The dataset on which we implemented the model and algorithms consists of 21,165 Chest X-Ray images. The dataset consists of 4 classes: COVID, Lung Opacity, Normal, Viral Pneumonia. We first rescaled each image from its original size of 299x299 to 70x70 as input shape for our CNN. We then split the dataset into 80% that constitutes to Training set (16,932 images) and 20% that constitutes to Testing set (4233 images). After that we normalized, and performed one-hot encoding.

We used various CNN models such as CNN using Conv2D, Max Pooling & Batch Normalization Layers, CNN using Conv2D & Max Pooling Layers, CNN using Conv2D, Max Pooling & Dropout Layers along with some state-of-the-art models such as Resnet – 152 V2 and DenseNet – 121. We also implemented various Traditional Machine Learning Models such as Decision Tree, Random Forest, SVM, K-Neighbors, Naïve Bayes, etc.

While training the CNN models, we also implemented some call back functions such as Early Stopping and ReduceLROnPlateau. Due to this, it is found that DenseNet-121 yielded the highest result, with accuracy % of 92.3. Early Stopping stops the fitting of the model before the specified no. of epochs if the monitoring parameter is not increasing/decreasing up to a certain no. of epochs. This helps in efficient usage of time as well as resources such as GPU time and RAM. ReduceLROnPlateau decreases the learning rate of the model if the monitoring parameter is not increasing/decreasing up to a certain no. of epochs. We have observed that reducing the learning rate does lead to better accuracy in training set as well as validation set, but only up to few reductions.

The reason DenseNet-121 has the highest accuracy (92.3%) on testing set is because there are shorter connections in between the layers, since each layer is connected to all other layers that are deeper in the network. Thus, it enables maximum information flow between the layers of the network. DenseNet-121 also combines the features by concatenating them and this is the reason it gave better accuracy as compared to Resnet-152V2 (91.54%) because in ResNet, features are combined through summation.

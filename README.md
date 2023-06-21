# TASK 5
I have tried to build a basic CNN model using the sequential API from keras for image classification into 10 categories.
The database can be downloaded from 
```
https://www.kaggle.com/competitions/cifar-10/data?select=train.7z
```

1.Installation and Imports:

The code begins by installing the py7zr package using !pip install py7zr.
Then, necessary packages are imported, including numpy, pandas, and other TensorFlow and Keras modules.

2.Unpacking Data:

The py7zr library is used to unpack the train.7z file into a directory called "temp".
This is achieved by registering the 7zip format and using shutil.unpack_archive().

3.Loading Data:

The trainLabels.csv file is read using pd.read_csv() and stored in the train_labels DataFrame.
The unique classes in the "label" column of the DataFrame are printed.

4.Model Architecture:

The code defines a convolutional neural network (CNN) model using the Sequential API from Keras.
Various layers such as Conv2D, BatchNormalization, and Activation are added to the model to construct its architecture.
The model ends with a Flatten layer to convert the 2D feature maps into a 1D vector and a Dense layer with softmax activation for classification.

5.Model Compilation:

The model is compiled using the compile() function.
The loss function is set to 'categorical_crossentropy', and the optimizer is set to 'adam'.
The metric used for evaluation is 'accuracy'.

6.Data Augmentation and Generators:

Two ImageDataGenerator objects, train_datagen and valid_datagen, are created.
train_datagen is configured with various augmentation options such as rotation, zoom, and shift.
valid_datagen is left with default settings.
Data generators train_generator and valid_generator are created using the flow_from_directory() method, specifying the directories, target size, and batch size.

7.Model Training:

The fit() method is called to train the model using the data generators.
The train_generator and valid_generator are provided as inputs for training and validation data, respectively.
The epochs parameter is set to 50, specifying the number of training epochs.
The steps_per_epoch and validation_steps are calculated based on the number of samples and batch size in the generators.
The training progress is displayed during the training process.


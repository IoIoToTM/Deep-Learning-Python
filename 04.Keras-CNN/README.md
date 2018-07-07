01. Simple CNN implementation to differentiate Cats and Dogs. [Dataset](https://www.kaggle.com/c/dogs-vs-cats/data) is taken from kaggle. Only 4000 images were taken for each category as such the model is not accurate.

02. Better approach to the Cats vs Dogs problem referenced from [here](https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html). To compensate for the small dataset image augmentation was used. Further, features were extracted using `VGG16` architecture and passed on to train `fc_layers` using `optimizer='rmsprop'` and  `loss='binary_crossentropy'`. 

03. Weights from the previous steps were saved and loaded (Transfer Learning). An increased accuracy was achieved `~.92`(for the dataset i was using) implementing `optimizer=optimizers.SGD(lr=1e-4, momentum=0.9)`

04. A simple method for visualing CNN Layers.

05. A better approach to visualing CNN layers referenced from [here](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html). More resources can be found [here](https://jacobgil.github.io/deeplearning/filter-visualizations) and [here](https://github.com/utkuozbulak/pytorch-cnn-visualizations)
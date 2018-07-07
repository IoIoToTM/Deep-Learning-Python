01. A simple Neural Machine Translation System developed from scratch using use a dataset of French to English corupus. The dataset is available [here](http://www.manythings.org). A simple encoder-decoder LSTM model was used in this problem. The model is trained using the efficient Adam approach to stochastic gradient descent and minimizes the categorical loss function. For further insights [this](https://machinelearningmastery.com/develop-neural-machine-translation-system-keras/) is a good start. I have referenced this project from the same. The dataset used was reduced to 15000 lines in the corpus due to my GPU Memory constraints. I will upload a quick start guide to train the same and all previous models on `floydhub` sometime in the near future.

02. This example implements generative model for text, character-by-character using LSTM recurrent neural networks in Python with Keras. [3 Men in a Boat](http://www.gutenberg.org/ebooks/308) was used as a dataset. This project is referenced from [here](https://www.analyticsvidhya.com/blog/2018/03/text-generation-using-python-nlp/).

Model Summary :
```
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
lstm_4 (LSTM)                (None, 100, 400)          643200    
_________________________________________________________________
dropout_3 (Dropout)          (None, 100, 400)          0         
_________________________________________________________________
lstm_5 (LSTM)                (None, 400)               1281600   
_________________________________________________________________
dropout_4 (Dropout)          (None, 400)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 60)                24060     
=================================================================
Total params: 1,948,860
Trainable params: 1,948,860
Non-trainable params: 0
_________________________________________________________________
..

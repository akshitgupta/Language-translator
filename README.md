# Language-translator

Problem Statement-

This problem can be thought as a prediction problem, where given a sequence of words in source language as input,
task is to predict the output sequence of words in target language.

Data cleaning steps-

1. Read the text and prepare the list of pairs of language phrases.
2. For cleaning the text, some of the operations for cleaning are:
--Remove the non printable charaters, if any
--Remove punctuations and non-alphabetic charaters
--Convert to lowercase

Preparing the data for training the model-

1. After cleaning the data, split the data in train and test.
2. Then, create separate tokenizer for both source language and target language.
3. After creating the tokenizer, encode and pad the input (source language) and output(target language)
   sequences w.r.t. their individual tokenizers and maximum sequence lengths.
4. Here, in this problem we will essentially be predicting the words in target language, therefore output seuences will need
to be converted in one hot encoding.


Define and train the RNN based Encoder-Decoder model-

1. First, we need to define the sequential model consisting mainly of two parts Encoder and Decoder
2. In Encoder, the input sequence shall be passed through an Embedding layer (to train the word embeddings for source
   language) and then the output from the Embedding layer may be passed through one or more RNN/LSTM layers.
3. Now, to connect this Encoder to Decoder (yet to be defined), we can use RepeatVector layer. (This is because the shape
   of the output by Encoder is not same as expected shape of Input by Decoder)
4. Now, stack up the Decoder, where in you may add one or more RNN/LSTM layers and nally the output TimeDistributed
   Dense layer to get output separately by timesteps.
5. Now, we have defined the model and now this can be trained on the training data, you prepared in last step. Here, you
   may play with the number of epochs, optimizer, batch size to get the optimum results.

Evaluating the model-

Use BLEU score for evaluating your model using NLTK library




# TV Script Generation

In this project, we'll generate our own [Seinfeld](https://en.wikipedia.org/wiki/Seinfeld) TV scripts using RNNs.  we'll be using part of the [Seinfeld dataset](https://www.kaggle.com/thec03u5/seinfeld-chronicles#scripts.csv) of scripts from 9 seasons.  The Neural Network you'll build will generate a new ,"fake" TV script, based on patterns it recognizes in this training data.

## Requirement
pytorch
python
numpy

### Step 1: Get the Data

The data is already provided  in `./data/Seinfeld_Scripts.txt` and we're encouraged to open that file and look at the text. 
>* As a first step, we'll load in this data and look at some samples. 
>* Then, we'll be tasked with defining and training an RNN to generate a new script!


### Step 2: prepare datasets
The first thing to do to any dataset is pre-processing. Implement the following pre-processing functions below:

1. Lookup Table
2. Tokenize Punctuation


### Step 3: Build the Neural Network
Implement an RNN using PyTorch's Module class. We may choose to use a GRU or an LSTM. To complete the RNN, we'll have to implement the following functions for the class:

1. __init__ - The initialize function.
2. init_hidden - The initialization function for an LSTM/GRU hidden state
3. forward - Forward propagation function.

The initialize function should create the layers of the neural network and save them to the class. The forward propagation function will use these layers to run forward propagation and generate an output and a hidden state.


### Step 4: Hyperparameters
Set and train the neural network with the following parameters:

Set sequence_length to the length of a sequence.
Set batch_size to the batch size.
Set num_epochs to the number of epochs to train for.
Set learning_rate to the learning rate for an Adam optimizer.
Set vocab_size to the number of uniqe tokens in our vocabulary.
Set output_size to the desired size of the output.
Set embedding_dim to the embedding dimension; smaller than the vocab_size.
Set hidden_dim to the hidden dimension of your RNN.
Set n_layers to the number of layers/cells in your RNN.
Set show_every_n_batches to the number of batches at which the neural network should print progress.


### Step 5: Train Loop¶
The training loop is implemented in the train_decoder function. This function will train the network over all the batches for the number of epochs given. The model progress will be shown every number of batches. This number is set with the show_every_n_batches parameter. we'll set this parameter along with other parameters in the next section.


### Step 6: Generate Text/Evaluation
To generate the text, the network needs to start with a single word and repeat its predictions until it reaches a set length. we'll be using the generate function to do this. It takes a word id to start with, prime_id, and generates a set length of text, predict_len. Also note that it uses topk sampling to introduce some randomness in choosing the most likely next word, given an output set of word scores!


### Step 7: Generate a New Script
It's time to generate the text. Set gen_length to the length of TV script you want to generate and set prime_word to one of the following to start the prediction:

1. "jerry"
2. "elaine"
3. "george"
4. "kramer"


### Step 8: Submitting This Project
When submitting this project, make sure to run all the cells before saving the notebook. Save the notebook file as "dlnd_tv_script_generation.ipynb" and save another copy as an HTML file by clicking "File" -> "Download as.."->"html". Include the "helper.py" and "problem_unittests.py" files in your submission. Once you download these files, compress them into one zip file for submission.

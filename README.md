# HeyJude
# Introduction 
HeyJude is a song generating deep learning model that uses LSTM (Long Short Term Memory), a specialised Recurrent Neural Network(RNN). It helps the fanatics of The Beatles band to be able to listen to songs that they would have made for us.Our aim is to create a trained model that is capable of generating lyrics similar to the previous lyrics of the famous pop group Beatles. 

# Table of Contents
1) Technologies Used
2) System Requirements
3) Set-up
4) Project Flow 
5) Future Implementations

# Technologies Used 
Front-end: As Hey-Jude is a ML project, it is implemented in Python. The model is trained in a corpus containing the song titles and the lyrics of many famous Beatle songs using RNN and LSTM. So, given a sequence of words from Beatle's lyrics, it can predict the next words. 

# System Requirements
1) The system should have Jupyter Notebook or Google Colab to run the ML model.

2) The required python packages are as follows, (here I have only mentioned the packages that I have used for the developments)
- tensorflow==2.3.1 
- numpy==1.18.5 

# Set Up

- Set up a virtual environment
- Install anaconda
- Pin your project dependencies
- Set up Jupyter Notebook
- Start lyricgenration.ipynb 


## Installing Python 
[Python](https://www.python.org/downloads/)

### UBUNTU
Ubuntu Linux 20.04 LTS includes Python 3.8.5 by default. You can confirm this by running the following command in the bash terminal:
 

      python3 -V
      Python 3.8.5
You can install pip3 in the bash terminal using:
 
      
      sudo apt install python3-pip
### MAC
macOS "El Capitan" and other more recent versions do not include Python 3. You can confirm this by running the following commands in the zsh or bash terminal to check upon installation:
 
      
      python3 -V
      Python 3.9.0
      
You can similarly check that pip3 is installed by listing the available packages:
 
 
      pip3 list
      
### Windows 
You can then verify that Python 3 was installed by entering the following text into the command prompt:


      py -3 -V
      Python 3.8.6
    
The Windows installer incorporates pip3 (the Python package manager) by default. You can list installed packages as shown:

  
      pip3 list

    

## Project Set Up 
1) The system should have anaconda setup before setting up Jupyter Notebook.
2) You can use Google colab if jupyter notebook is not handy. 
       
## Project Flow 
RNNs, like most other forms of neural networks, require a starting state before they can begin the prediction. In this situation, the initialization is symbolised by a starting string that will serve as the beginning of the lyrics that are created. Using the beginning string and RNN state, the model calculates the probability distribution of the subsequent word. The predicted word is then utilised as the input for the following time step of the model after the index of the predicted word is determined using categorical distribution. 

In order to assist the RNN by giving more context, the state that the RNN returns is then sent back to the input of the RNN. As it continues to make predictions, it trains more effectively because it has more context provided by the predicted words.The corpus (PMP.txt) comprises several MJ songs' titles and lyrics. I personally generated the corpus using the web lyrics that I discovered. 

Training data require some preprocessing, as with practically any machine learning model, before they are ready to be utilised as a training input for the RNN. Initially, we preprocess the corpus via:
- Make all the letters lowercase. 
- Remove all white space 
- Remove all special characters, including "," "(," "")," "[," "]," etc.

Turning to the next word list once the text has been preprocessed, t he term "Tokenization" also applies to this process. 
After that, we removed all the subsequent spaces or tabs from each word. Later, we identified the whole vocabulary that made up our dataset.  We then encode words as integers in order to train the model. The entire corpus is then represented as a list of numbers.

### Model 
The RNN model consists of three layers: 
1) Input Layer:  It converts the integer corresponding to each word into a vector whose dimensions are known.  
2) Middle GRU layer: Gated Recurrent Units are referred to as GRUs. This layer precisely specifies how many units it includes.
3) A Long Short-Term Memory (LSTM) layer : It may alternatively be used in place of this layer. 
4) Result layer: It has the same number of units as the vocabulary size.

## Future Implementations
1)The lyrics can be later be passed on into a speech converter using wavenet to create a complete song, carrying the voice and words of Beatles. 
2)The model can be reused for the famous Micheal Jackson songs to generate lyrics by changing the data to MJ Lyrics.

Song Lyrics Generator
======
![stars](https://img.shields.io/github/stars/samirsalman/SongLyricsGenerator?style=plastic) ![lastcommit](https://img.shields.io/github/last-commit/samirsalman/SongLyricsGenerator) [![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/donate?hosted_button_id=7HWMJSGMCCTB6)

![logo](https://github.com/samirsalman/SongLyricsGenerator/blob/main/logo.png)

**Song Lyrics Generator is a Deep Learning model, particularly an RNN model, it is able to generate music lyrics starting from a string input.**

### If you like the project, please give it a star. 

![star](https://img.pngio.com/small-star-3-200-x-200-making-the-webcom-black-star-small-png-200_200.png)

## Description
Song Lyrics Generator is an RNN model, it is able to predict a song lyrics starting from an input string. An RNN model is a Deep Learning model, designed for Sequence-based tasks. 
The problem of generating the lyrics of a song from an input is modeled as predict next word multiple times, from the input to a fixed length text.

## Data
The data used in this project is aviable at https://www.kaggle.com/paultimothymooney/poetry.
The dataset contains different song lyrics of multiple artists, like: 
> Kanye West, Lil Wayne, Adele, Beatles 

Song Lyrics Dataset contains a file for each artist and each file contains different song lyrics of the artist. The total number of artists is 49.

## Model

Like mentioned before we used an RNN model. 

![rnn](https://miro.medium.com/max/627/1*go8PHsPNbbV6qRiwpUQ5BQ.png)

RNN is a particular type of Neural Network, it is very usefull for sequence-based tasks or time series tasks. RNNs can take one or more input vectors and produce one or more output vectors and the output(s) are influenced not just by weights applied on inputs like a regular NN, but also by a “hidden” state vector representing the context based on prior input(s)/output(s).

The RNNs equations are the following:

![equations](https://miro.medium.com/max/558/1*55c3opV_tqm3wUwcj0m-jg.png)

Where:
```
- x(t) is the input at time t
- h(t) is the hidden state at time t, we can imagine it like a "memory"
- o(t) is the output at time t
- y(t) is the softmax of o(t)
- W, V and U are the network weights
```

**Song Lyrics Generator** model is the following:

![model](https://github.com/samirsalman/SongLyricsGenerator/blob/main/model.PNG)


Where embedding layer create the embedding of the input text, GRU is a type of RNN similar to LSTM but with fewer parameters, at the end the Output layer is a simple Dense Layer.

The parameters of the network are:

```
# Length of the vocabulary in chars
vocab_size = len(vocab)

# The embedding dimension
embedding_dim = 256

# Number of RNN units
rnn_units = 1024
```

## Example

INPUT: ```It's a rain day```

OUTPUT: 
```
It's a rain day
I'd love somebody for me My body [Chorus: x2] Delirious
(Yeah!)
(all night long)
Tell me what's new all again
(Bring the night is gone)
Why do niggaz?
Lett! This Korn Nos Foreward
Jaber not gonna go out nuttift
Prove that magic first chance
I wake up in a truer, sir, [Missy] No show, Maria, mamamage of a frage
And still, his spot tank (yeah)
Your gotta lose heard of kisses
I ain't saying you want to tell her hoe
Young and Id I got niggled in the risk
They say I'm the baddes, monster brings you goodless plan, I'm not too old bag its got an I skin
All birthday, all night (Woo, ah, ah, ah, a-ay-ay-ay-ay-ay-ay)
Alone shall Uhhuh but we suck him up
Well, I may be the only girl
And I'm a liabi-a-Beck it goe
It's been a long time
Since I cant never even sellion who u done
See now you're the liquor without your baby
Nobody but you, baby
Yeah, yeah, niggas know what it goes (arejbosh 'Cause that's making some change sense Oh boy, ot can cut you down) (I still go, to you who and you'll
```

## Use the model

To use the model you must download "model" folder from this repository and then use this function to load the model:
```python
from tensorflow import keras

def get_trained_model(model_path): 
  model = keras.models.load_model(model_path)
  return model

```
**model_path is the path where you downloaded model folder**


## Kaggle Notebook
* [Version 1.0](https://www.kaggle.com/samirsalman97/songlyrics)

## Author
**Samir Salman**

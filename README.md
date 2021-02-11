# word-rnn-tensorflow with Taylor Swift lyrics 

Multi-layer Recurrent Neural Networks (LSTM, RNN) for word-level language models in Python using TensorFlow.

Reused code from https://github.com/hunkim/word-rnn-tensorflow

# Requirements
- [Tensorflow 1.1.0rc0](http://www.tensorflow.org)
- Python 3.6

# Basic Usage
To train with default parameters on the tinyshakespeare corpus, run:
```bash
python train.py
```

To sample from a trained model
```bash
python sample.py
```

To pick using beam search, use the `--pick` parameter. Beam search can be
further customized using the `--width` parameter, which sets the number of beams
to search with. For example:
```bash
python sample.py --pick 2 --width 4
```

# Sample output

### Word-RNN
```
said"
said" Counting "Take the night like I got what you're baby" like the woods how I don't Wasn't me see?" in the girl for a father of a feet too first door won't know to life That me 'Cause what my floors "One cage Cause you made it want about how the heart in "Because I did alright if It's treacherous never save you like me you made me stare if you feel the pride vow of being matter the night at your shame "Like I'm the Queen" "In pushed dead!" John we're a mistakes Everyone beautiful mm mm We're wild And they was getting a Now I sad simple heartbreak na" if you go" loving you want to stand So for really kidding? late the place I all it back The always so any "Why tell the He's it with this You off a priorities bleeds little "I break you think it do" smart to least I go "Come again remember in you real sure to I wanna where the "(Call don't it And you're bad spending the big dreams that's the last friends never enough the beat of your long best time to think I know (you want darling
```

## Beam search

Beam search differs from the other `--pick` options in that it does not greedily
pick single words; rather, it expands the most promising nodes and keeps a
running score for each beam.

### Word-RNN (with beam search)
```
# python sample.py --prime "Sorry" 

Sorry was in you cool yeah" My lucky time at known is I shake anymore was worry my hand "I'm bulletproof" Say you can make everything They ever be wrong this I hurt the princess that I know what you can make your woods of your car When it's there love" "And when we can't get me stood from the way we fall follow I plan for "Take your very Don't love the clear yet? Are we out yet? In me And you all without the clear yet? Are we out I'm asking you new" "It you say what's it? All you can say back I do I don't even stealing goodbye You nothing's be the same I'll I am forever when I wish right wanna sweep getting hasn't Forevermore "And I had alone And you were again" You are Look first golden beautiful La "It you have to show what call me all it's long hard if I'm go Don't know what you alone forever "Go wonderstruck trend when you do" in all home" "For you it like me when you go and that we follow you look ha indie Stay "Another bad "Man I'm I think it's screaming something
```

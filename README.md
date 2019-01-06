# Tweekenizer

This repository hosts the code for a tokenizer of tweets. It's main purpose is to identify subtle profanity, so it should
obtain better performance on data containing hidden profanity (e.g. 'f*ck').

Disclaimer: The following paragraphs may contain profanity.

## Description

Python offers a set of sentence tokenizers for different purposes: nltk's word tokenizer, spacy's, scikit-learn's default and 
TweetTokenizer, among others. All but TweetTokenizer disregard hashtags and mentions by separating the symbols from the rest of the token(s).
Although TweetTokenizer considers the Twitter *dialect*, it fails to tokenize subtle hidden profanity.

For the word ```f*ck```,the tokens considered are ```[f, *, ck]```. The word ```g@y``` is tokenized as ```[g, @y]```, considering 
a single token ```g``` and a wrongly identified mention ```@y```. While the hashtag ```#hash_tag``` is correctly tokenized as 
```[#hash_tag]```, *regular* tokens are not underscore separated: ```love_twitter``` is tokenized as ```['love_twitter']``` instead of ```['love', '_', 'twitter']```.

Tweekenizer was created in order to enable a proper identification of hidden profane words, considering the features detailed above. Applying distance related features, i.e. levenshtein distance to slang words should output better results using this tokenizer.

## Installation

**Using pip**

Soon to be released as a Python package.

**Clone repository**

https://github.com/Guilherme-Routar/Tweekenizer.git

## Usage


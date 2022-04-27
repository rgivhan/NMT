# Neural Machine Translation of Cherokee to English using RNNs

Cherokee is spoken by only ~2000 as their first language, and of these speakers, only a handful are under the age of 40. Compared to other machine translation pairs, Cherokee-English is a low-resource language with only ~14K sentence pairs avaialable. It is an interesting language for many reasons: 

* It is polysynthetic (many morphemes are stitched together to form a word)
* It is gender-neutral
* Verbs comprise 75% of the language (compared to 25% for English)

Machine translation efforts, such as those by Zhang et al. (https://arxiv.org/abs/2010.04791), are essential to the preservation and revitalization of the language. We present our effort here.  

## Architecture
We use a Seq2Seq network with multiplicative attention to build an NMT system. Our training procedure uses a Bidirectional LSTM Encoder, a Unidirectional LSTM Decoder, and a cross entropy loss function. Sentences are encoded at the sub-word level, as Cherokee is a polysynthetic language and so morpheme meaning in Cherokee often corresponds to word meaning in English.

## Output and Results
We achieve a BLEU Score of 13.18. This is impressive considering our limited training data. Zhang et al. used multilingual training data to alleviate the low-resource constraint and achieved a similar score of ~15. 

## How to Run

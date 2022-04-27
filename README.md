# Neural Machine Translation of Cherokee to English using RNNs

## Architecture
We use a Seq2Seq network with multiplicative attention to build our NMT system. Our traning procedure uses a Bidirectional LSTM Encoder, a Unidirectional LSTM Decoder, and a cross entropy loss function. 

## Why Cherokee?
Cherokee is spoken by only ~2000 as their first language, and of these speakers, only a handful are under the age of 40. Compared to other machine translation pairs, Cherokee-English is a low-resource language with only ~14K sentence pairs avaialable. It is an interesting language for many reasons: 

* It is polysynthetic (many morphemes are stitched together to form a word)
* It is gender-neutral
* Verbs comprise 75% of the language (compared to 25% for English)

Machine translation efforts, such as those by https://arxiv.org/abs/2010.04791, are essential to the preservation and revitalization of the language. We present our effort here.  

## Output and Results

## How to Run

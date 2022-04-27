# Neural Machine Translation of Cherokee to English using RNNs

Cherokee is spoken by only ~2000 as their first language, and of these speakers, only a handful are under the age of 40. Compared to other machine translation pairs, Cherokee-English is a low-resource language with only ~14K sentence pairs avaialable. Training pairs mostly come from a Cherokee dictionary as well as several editions of the New Testament and Psalms of the Bible. Cherokee is an interesting language for many reasons: 

* It is polysynthetic (many morphemes are stitched together to form a word)
* It is gender-neutral
* Verbs comprise 75% of the language (compared to 25% for English)

Machine translation efforts, such as those by Zhang et al. (https://arxiv.org/abs/2010.04791), are essential to the preservation and revitalization of the language. We present our effort here.  

## Architecture
We use a Seq2Seq network with multiplicative attention to build an NMT system. Our training procedure uses a Bidirectional LSTM Encoder, a Unidirectional LSTM Decoder, and a cross entropy loss function. Sentences are encoded at the sub-word level, as Cherokee is a polysynthetic language and so morpheme meaning in Cherokee often corresponds to word meaning in English. We used **PyTorch**. 

![Model Architecture](https://github.com/rgivhan/NMT/NMT_diagram.png)

## Output and Results
We achieve a BLEU Score of 13.18. This is impressive considering our limited training data. Zhang et al. used multilingual training data to alleviate the low-resource constraint and achieved a higher but similar score of ~15. 

### Example output
**Cherokee input:** 
ᎡᏆᎭᎻ ᎯᎠ ᏄᏪᏎᎴᎢ; ᎼᏏ ᎠᎴ ᎠᎾᏙᎴᎰᏍᎩ ᏚᏁᎭ; ᎾᏍᎩ ᏫᏓᎾᏛᏓᏍᏓᏏ.
“ᎭᏩ ᏍᎩᏉᏗ ᏄᏍᏕᏍᏗ, ᎡᏚᏥ.” ᎤᏛᏁ ᏌᎳᏓ.
ᎾᏍᎩ ᎢᏳᏍᏗ ᏞᏍᏗ ᎢᏣᏓᏄᎸᏗᏉ ᏱᎨᏎᏍᏗ, ᏗᏥᏍᏓᏩᏕᎩᏍᎩᏂ ᎨᏎᏍᏗ ᎾᏍᎩ Ꮎ ᎤᏃᎯᏳᏒ ᎠᎴ ᏗᏅᏂᏗᏳ ᎨᏒ ᎠᏅᏗᏍᎬ ᎤᎾᏤᎵ ᏄᏅᏁᎸ ᎠᏚᎢᏍᏔᏅᎢ.
ᎭᎾᎾ ᎦᏙᎬ, ᎪᎱᏍᏗ ᎠᎵᏖᎸᎮᏍᎬ ᎤᎪᎮᎢ.

**English Test Translation:**
But Abraham saith, They have Moses and the prophets; let them hear them.
“Very well, Uncle,»” replied Charlotte.
that ye be not sluggish, but imitators of them who through faith and patience inherit the promises.
As he stood there, he noticed something move.

**NMT Output Translation:**
Abraham said unto him, Moses and the prophets: that he might be fulfilled.
“You'll be sorry,” said Charlotte.
Wherefore be not afraid, because of them of them, but by their faith and in patience.
So he came to him, he was nothing to see something.

## How to Train and Test
This repo comes with pre-trained parameters and test outputs. If you'd like to re-train and re-test after adapting the model, use these commands. 

**To train** run: 
```
sh run.sh train
(Windows) run.bat train
```


**To test** run: 
```
sh run.sh test
(Windows) run.bat test
```

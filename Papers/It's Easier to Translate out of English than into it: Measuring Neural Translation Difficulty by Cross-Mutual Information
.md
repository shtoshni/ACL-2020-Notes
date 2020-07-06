# It's Easier to Translate out of English than into it: Measuring Neural Translation Difficulty by Cross-Mutual Information
## By Emanuele Bugliarello, Sabrina J. Mielke, Antonios Anastasopoulos, Ryan Cotterell, Naoaki Okazaki

* BLEU scores indicate the accuracy of translation.
* However, there are issues with using BLEU for cross-lingual comparisons:
    * Based on the notion of "word". More partial credit for languages with more tokens.
* Look at the likelihood?
* *Both BLEU and likelihood conflate the difficulty of understanding source language and generating in target languages!*
* Mutual information to the rescue!
    * MI(S; T) = H(T) - H(T|S)
    * Use LM model for first term and translation model for second term.
    * High MI means easier/better translation ie the source sentence was able to reduce the "confusion" more.
* My commentary:
    * Confused about why cross-entropy is not enough and why mutuak information is needed.
    * From the paper chat it seems a lot of people have issues with the paper.
        * Some are questioning the experimental choices such as sharing embeddings.
        * Some are questioning the metric.

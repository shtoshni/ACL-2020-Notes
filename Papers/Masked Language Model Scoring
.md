# Masked Language Model Scoring
## By Julian Salazar, Davis Liang, Toan Q. Nguyen, Katrin Kirchhoff

* BERT as a generative model.
* Pseudo-log-likelihood score (PLL), summation of score's with one word masked out at a time.
* Possible to finetune BERT to compute PLL in a single inference rather than mask out one token at a time.
* Rescoring of N-best hypotheses by MLM models gives edge over pure LM models like GPT-2.

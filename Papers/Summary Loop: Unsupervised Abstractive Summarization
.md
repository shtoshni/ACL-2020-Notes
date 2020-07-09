# The Summary Loop: Learning to Write Abstractive Summaries Without Examples
## By  Philippe Laban, Andrew Hsi, John Canny, Marti A. Hearst

* Summary is a brief, fluent text that covers main points of source document.
* Model working:
    * Provide target length (brevity)
    * Summarizer summarizes the document given the target length.
    * Next the document is masked.
    * The masked document and summary are provided as inputs to the coverage model which fills in the masked tokens - Coverage score.
    * The summary's fluency is evaluated using a pretrained LM model - Fluency score.
    * RL model optimizes for coverage score + fluency score.
*  Model details:
    * Salient words are masked - saliency based on tf-idf. All occurrences are masked out for a selected word type.  
    * Coverage model is a finetuned-BERT model.
    * Finetuned GPT2 model for fluency. Log-likelihood normalized between [0, 1] (Need to see the details). Important step!
    * Summarizer is a GPT2 models. Stops when the model produces END token.
    * Coverage and Fluency model are frozen during Summarizer training.
    * Trained with Self-Critical Sequence Training.
* Approaches supervised model results without seeing any examples!
* Summary loop results are more abstractive than previous models.

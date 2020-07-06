# On Faithfulness and Factuality in Abstractive Summarization
## By Joshua Maynez, Shashi Narayan, Bernd Bohnet, Ryan McDonald

* Abstractive summarization models can hallucinate information.
* Goals of the paper:
    * What types of hallucinations occur?
    * How often they occur?
    * Automatic means of measuring hallucinations?
    * How can models avoid generating hallucinations?
* Types of hallucinations:
    * Intrinsic hallucination - Misrepresent the information
    * Extrinsic hallucination - Add information not inferrable from the document.
    * Hallucinations might not be wrong (categorized as factual) - Might be captured by pretrained models.
* How often?
    * Use human evaluation.
    * Dataset used XSum
    * A lot of extrinsic hallucinations. Even gold has *73% extrinsic hallucinations*.
    * Best systems are faithful/factual only 35% of the time! -- I don't understand why Gold does so badly, need to read the paper.
    * Pretraining improves factuality and faithfulness.
* Automatic means of measuring hallucinations:
    * Rouge, BERTScore don't correlate well with human annotations.
    * *Entailment scores are better correlated (still around 0.4)*
* Avoid generating hallucinations:  
    * Select summaries (among 4 summaries) based on probability that summary is entailed by document.
    * Improves faithfulness and factuality but performance decreases on automatic metrics.

# Exploring Content Selection in Summarization of Novel Chapters
## By Faisal Ladhak, Bryan Li, Yaser Al-Onaizan, Kathy McKeown

* Chapters difficult to summarize:
    * Long form summarization.
    * Variation in literary style.
    * Lead baselines don't work well; Extreme paraphrasing.
* Proposed dataset derived from Gutenberg:
    * ~8K chapters.
    * Online study guides for summary. 2-5 summaries per chapter
    * ~7x length of the news data.
* Authors focus on extractive summarization:
    * Similarity metric for alignment with the abstractive summary.
    * Alignment method.
* Best similarity metric - Rouge-weighted (weight words differently and average R-1,2,L)
    * BERT similarity didn't work well (I think it might be due to not finetuning BERT)
    * Crowdworkers prefered R-wtd over other metrics.
* Alignment method - Stable matching.
* Automatic metrics and human preference aligns for both the similarity metric and alignment method.
* However, automatic metrics prefer constituent level extracts whereas humans prefer sentence level extracts.

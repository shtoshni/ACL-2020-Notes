## Structural Analysis: Probing
* Probing classifiers often linear.
* In NLP often the probing task is about testing the linguistic info captured by neural models.
* Case Analysis MT
    * Morphological knowledge in lower layers while syntactic and semantic knowledge in upper layers. A combination of layers (concatenation?) has the most information.
    * Baselines:
        * Static word embeddings, random features
    * Skylines:
        * SOTA models for the probing task
* Limitations of Probing:
    * How complex can the probing model be?

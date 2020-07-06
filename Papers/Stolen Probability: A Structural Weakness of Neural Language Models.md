# Stolen Probability: A Structural Weakness of Neural Language Models
## David Demeter, Gregory Kimmel, Doug Downey

* *Dot-product softmax is a structural weakness of NLM.*
* Dot product distance metric introduces a limitation that bounds the expressiveness of NNLMs, enabling some words to "steal" probability from other words simply due
to their relative placement in the embedding space.
* Infrequent words have smaller norms and end up inside the convex hull of embedding space.
* Impossible for NLM to assign a high probability to infrequent words.
* Commentary:
    * Super cool work and very easy to understand.
    * How would other distance metrics do? 

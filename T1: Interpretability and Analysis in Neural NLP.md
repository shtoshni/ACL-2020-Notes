## Structural Analysis: Probing Classifiers
* Probing classifiers often linear.
* In NLP often the probing task is about testing the linguistic info captured by neural models.
* Case Analysis MT
    * Train a MLP on encoder representations of an neural MT system.
    * Morphological knowledge in lower layers while syntactic and semantic knowledge in upper layers. A combination of layers (concatenation?) has the most information.
* What to compare probing accuracy against?
    * First set of comparisons:
        * Baselines:
            * Static word embeddings, random features
        * Skylines:
            * SOTA for the probing task, or a full-fledged model
    * Compare against a control task, say one with random labels [Hewitt and Liang, 2019](https://www.aclweb.org/anthology/D19-1275.pdf):
        * Good probe should be "selective": high accuracy at linguistic task and low accuracy at control task.
* Complexity of Probing Models:
    * Common choices linear and simple MLP models.
    * How complex can the probing models be?
        * [Pimentel et al, 2020](https://arxiv.org/pdf/2004.03061.pdf) argue to choose the most complex probing model.
    * Simple models still useful for measuring "ease of extraction"
    * [Voita and Titov, 2020](https://arxiv.org/pdf/2003.12298.pdf) account for both probe complexity and accuracy:
        * Minimum description length (MDL) - Bits required to transmit model + label


## Behavioral Analysis: Creating Probing Test Suites
* Focusses on the long tail phenomena. Standard evaluation can hide these artifacts.
* Construct challenge sets aka test suites to cover diverse phenomena.
* Benefits:
    * Model-agnostic. Model is treated as a "black box".
    * "Squinting at the data": If you go looking for some patterns in probing, you might find those patterns (like attention)
    * More practical than structural probes as you care about the end result.
* Limitations:
    * *What's limiting generalization? Model or training data?*
    * Only know the end result. Can't explain how the model solved or why the model failed?
    * Probing sets can have artifacts.
    * Risk of overfitting to challenge sets.
* How to test model on probing set?
    * Ideally with no/minimal finetuning - Risk of overfitting to probing set.
* Categories of test suites:
    * Tightly controlled:
        - Create minimal pairs where the pairs differ on a few words/properties.
        - Pro - Few confounds; Con - Hard to generate/awkward
    * Loosely controlled:
        - Average performance over diagnostics sets with properties of interest.
        - Pro - Natural examples; Con - Can be (un)lucky with data distribution.
    * Adversarial split:
        - Design adversarial data with (minimal) edits/perturbations.
        - Pro - Practical analysis of model; Con - Tightly coupled to model.  
* The dataset can be constructed manually, semi-automatically (template), or fully automatically.


## Interactive Visualizations
*  "Playing" with model to form hypothesis and accelerate understanding.
    * Can help reduce the exploration space of models and hypotheses.
*  Visualization of models can generate trust in the user.
*  Categories of Visualization:
    * Task:
        * Understanding model structure
        * Understanding model decisions
    * Model involvement:
        * Passive observation - Tensorboard
        * Interactive observations - Model output visualization
    * End user visualization
        * For eg, visualization for a medical professional.
* Limitations:
    * Time consuming. Impossible to make them useful across tasks.
    * It's just an additional step in analysis. Accepting hypothesis requires further investigation.

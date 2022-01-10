# RaFoLa: Rationale-Annotated Corpus for Detecting Indicators of Forced Labour

Forced labour is the most common type of modern slavery, affecting at least 24.9 million people worldwide [[1]](#1). We focus our work on multi-class and multi-label text classifiers for identifying forced labour indicators and attempt to make their predictions more understandable.

This repository presents, to the best of our knowledge, the first openly accessible English corpus annotated for multi-class and multi-label forced labour detection.

Our goal is to provide richer annotations for training text classification models, i.e., labels with rationales [[2]](#2). When annotating a news article, our annotators also highlight the evidence supporting their annotation, thereby allowing classifiers to learn \emph{why} the instance belongs to a certain category.

## Data Annotation

We developed an annotation scheme to guide annotators in labelling news articles. The scheme is based on the 11 indicators of forced labour defined by the ILO [[3]](#3). These indicators are intended to help law enforcement officials, labour inspectors, and NGO workers to identify persons who are possibly trapped in a forced labour situation. For a detailed description of the indicators of forced labour and examples for each one of them, we refer the reader to the **Annotation Guidelines**.

## Corpus

The corpus consists of **989 news articles** retrieved from specialised data sources and annotated according to the annotation schema detailed in the Annotation Guidelines.

The JSON file is structured as follows:

- **Index**: News article ID (Integer).
- **Title**: News article title (String).
- **Content**: News article content (String).
- **Labels**: List of labels suitable for multi-class multi-label classification.
- **Set**: String detailing the role of the example in classification experiments (train, validation and test set).
- **Rationales**: List of rationales, specifyng both the text and label for which the rationales were provided.

## Text Classification

### Installation

You need to have Python 3.7 [[4]](#4) or higher installed. It is recommended that you use a virtual environment:

```
sudo pip3 install -U virtualenv
virtualenv --system-site-packages -p python3 ./my_venv
source ./my_venv/bin/activate
```

Install all required Python packages using:

```
pip install -r requirements.txt
```

Clone the repository:

```
git clone https://github.com/emendezguzman/rationales_for_detecting_forced_labour.git
```

### Classification Experiments

The classification experiments were performed with the aid of the [Simple Transformers](https://simpletransformers.ai/) library, a Python package based on the Transformers library by HuggingFace [[5]](#5).

### Hyperparameter Tuning

We split the data set into training, validation and test sets according to a 70:10:20 ratio and search the hyperparameter values that minimise the function loss over the validation set. To optimise the training process, we tuned the model hyperparameters using a random search method and run a total of 40 training runs using WandB [[6]](#6). For more details about the implementation please refer to **hyperparameter_tuning.ipynb**.

### Model Evaluation

Finally, we employed four metrics to evaluate the performance of our baseline classifiers: F1 Score (F1), Label Ranking Precision Average Precision Score (LRAP), and Exact Match Ratio (EMR) [[7]](#7). For details about the implementation please refer to **evaluation.ipynb**.

## References

<a id="1">[1]</a> 
Landman, T. and Silverman, B. (2019). 
Globalization and modern slavery. 
Politics and Governance 7, no. 4: 275-290.

<a id="2">[2]</a> 
Lei, T., Barzilay, R. and Jaakkola, T. (2016). 
Rationalizing neural predictions. 
arXiv preprint arXiv:1606.04155.

<a id="3">[3]</a> 
International Labour Organization. (2012). 
ILO Indicators of Forced Labour. In: Special Action Programme to Combat Forced Labour.
Special Action Programme to Combat Forced Labour.

<a id="4">[4]</a>
Van Rossum, G. and Drake, F. (2009).
Python 3 Reference Manual
CreateSpace.

<a id="5">[5]</a>
Wolf, T. et al. (2019).
Huggingface's transformers: State-of-the-art natural language processing
arXiv preprint arXiv:1910.03771

<a id="6">[6]</a>
Biewald L. (2020).
Experiment tracking with weights and biases
Software available from wandb.com

<a id="7">[7]</a>
Feldman, R. and Sanger, J. (2007).
The text mining handbook: advanced approaches in analyzing unstructured data
Software available from wandb.com

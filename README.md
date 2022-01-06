# RaFoLa: Rationale-Annotated Corpus for Detecting Indicators of Forced Labour

Forced labour is the most common type of modern slavery, affecting at least 24.9 million people worldwide [[1]](#1). We focus our work on multi-class and multi-label text classifiers for identifying forced labour indicators and attempt to make their predictions more understandable.

This repository presents, to the best of our knowledge, the first openly accessible English corpus annotated for multi-class and multi-label forced labour detection.

Our goal is to provide richer annotations for training text classification models, i.e., labels with rationales [[2]](#2). When annotating a news article, our annotators also highlight the evidence supporting their annotation, thereby allowing classifiers to learn \emph{why} the instance belongs to a certain category.

## Annotation

We developed an annotation scheme to guide annotators in labelling news articles. The scheme is based on the 11 indicators of forced labour defined by the ILO [[3]](#3). These indicators are intended to help law enforcement officials, labour inspectors, and NGO workers to identify persons who are possibly trapped in a forced labour situation. For a detailed description of the indicators of forced labour and examples for each one of them, we refer the reader to the Annotation Guidelines.

## Documentation

The corpus consists of **989 news articles** retrieved from specialised data sources and annotated according to the annotation schema detailed in the Annotation Guidelines.

The JSON file is structured as follows:

- **Index**: News article ID (Integer).
- **Title**: News article title (String).
- **Content**: News article content (String).
- **Labels**: List of labels suitable for multi-class multi-label classification.
- **Set**: String detailing the role of the example in classification experiments (train, validation and test set).
- **Rationales**: List of rationales, specifyng both the text and label for which the rationales were provided.

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



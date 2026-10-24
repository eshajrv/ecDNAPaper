# Detecting Cancer-Causing ecDNA

Predicting whether a tumor sample carries **extrachromosomal DNA (ecDNA)**, circular DNA that drives oncogene amplification and drug resistance, from tabular genomic features.

Compares three classifiers with stratified k-fold cross-validation, upsampling the rare ecDNA class (about 1% of samples):

| Model | Mean ROC AUC |
|---|---|
| Logistic regression | **0.93** |
| Random forest | 0.92 |
| Neural network (Keras, dense) | 0.50 |

The notebook (`CodeDocumentation.ipynb`) covers loading the data, resampling, training each model, confusion matrices, and ROC curves averaged across folds. Because ecDNA is so rare, AUC and per-class recall matter more here than accuracy. Every model scores about 99% accuracy just by predicting "no ecDNA".

**Stack:** scikit-learn · TensorFlow/Keras · pandas · matplotlib (Google Colab)

The source table (`bb-ecDNA-master-table.tsv`) is not included in this repo.

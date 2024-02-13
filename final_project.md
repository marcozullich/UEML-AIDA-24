# Instructions for the final project

In the final project, you are tasked with building a few Deep (Bayesian) Neural Networks on a problem of your choice (classification or regression), then to evaluate the reliability and the out-of-distribution (OOD) detection capabilities of such models.

The deadline is set to **Sunday, February 25th 2024 23:59 Anywhere-on-Earth**.

Please deliver the project as a Jupyter Notebook, with/without usage of helper Python scripts within the same folder.

## Choice of dataset

The dataset should possibly not be a toy dataset (e.g., no MNIST, sinusoid approximation, etc.). 
If you have doubts on the selection of the dataset, please contact us.
In making the choice, consider also that, for the OOD detection part, you should also find an OOD dataset usable for the task (refer to the slides for lecture 4 for details on this).

The dataset should be **split in train/validation/test** datasets.

## Models training

You should train a **frequentist DNN** to solve a problem, than 2 or 3 (depending on the difficulty of the task) BNNs.
Try to have one model for each of the following groups: **Dropout/Dropconnect**, **Deep Ensemble**, **VI/Flipout**.
Calculate the performance (accuracy/MSE/MAE/F1 score, or whichever metric you deem fit) on the test set and comment.

## Reliability (calibration)

Evaluate the reliability of these 3/4 models: plot a **reliability diagram**, then calculate the **expected calibration error** on the test set.
Comment on the reliability of each of the models.

## OOD

Evaluate the OOD capability of the 3/4 models: find (or generate) a relevant OOD dataset, split it in validation/test, assess the detection capability on the 2 validation sets and report the Area Under the ROC Curve. Comment on the result.

### Thresholding for filtering OOD data

Determine the **threshold for classifying a data point as ID/OOD**: decide on a metric (e.g., F1 score) for determining the threshold on confidence/entropy of the model output.
Select the threshold based on the results on the validation splits.

For evaluating the OOD detection performance, **compute the predictions on both the test sets** (for in-distribution and OOD data) and then report the F1 score (or whichever metric you chose for determining the threshold).
Comment on the result.
Is the result satisfactory?
Does the accuracy/performance of the model change considering only ID data, while withholding the predictions for data below the threshold you found?


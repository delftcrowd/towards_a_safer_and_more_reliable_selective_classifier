# Towards a Safer and More Reliable Selective Classifier

### Basic information

- Name of Student: Xinyue Chen
- Names of Supervisors: Jie Yang
- Academic Year: 2022

### Introduction
While the performance of traditional confidence-based rejectors is heavily dependent on the calibration
of the pretrained model, this study proposes the concept of feature-based rejectors and the whole
pipeline where such rejector can be used in. Multiple design and development decisions along the
implementation are discussed in the paper - involving humans in the loop of creating the feature set
that machine should use and defining value, using interpretability methods such as saliency map to
extract the features that the machine actually uses, and SceneRejector is the end product of the whole
process. It is relevant to the field of computer vision, and it is applied to the task of scene classification
within the scope of this paper. Its performance is evaluated against baselines with accuracy, rejection
rate, and a new metric named value, which more comprehensively measures the practical value of
machine learning with a reject option in different use cases. Experiments have proved the concept of a
feature-based rejector works and it is able to filter out unknown unknowns, which is a challenge to the
confidence-based rejectors. It also creates better value than the traditional confidence-based rejectors
in some cases, especially when the machine learning model is not well calibrated. Further analysis is
conducted to understand the behavior of SceneRejector as well. It is discovered that SceneRejector
brings better value than confidence-based rejectors when the pretrained model is not well calibrated,
and that rejection rate and accuracy of the rejector is also correlated with the value.

### Research summary
For a safer and more responsible machine learning pipeline, confidence-based rejectors are commonly
used to safeguard machine decisions. However, rejectors of this type cannot filter out high-confidence
errors, i.e. unknown unknowns, and it heavily relies on the calibration of the classifier as well. This study
proposed and implemented a feature-based rejector, SceneRejector, and embedded it in a selective
classifier. Such rejector is pluggable to any pretrained classifier as long as the task and the classes stay
the same. There is a training pipeline to train the rejector and a testing pipeline to apply the rejector. The
training pipeline consists of three components: 1) input from a pretrained classifier, which means the
features that the classifier uses while making a prediction; 2) "should know" extraction, which involves
humans in the loop and acquires the features that the classifier should use to make a prediction; 3)
rejector training, where we train a decision tree with the input and output are prepared from the previous
two parts and the ground truth. The testing pipeline consists of two parts, the first of which is the same
as the training pipeline, and the second of which is simply applying the trained rejector with input from
the first part. Several design decisions are made based on experiments. It is important to note that
human knowledge can not only be used in "should know" extraction, but also in defining the created
value, even though this study did not involve humans in the latter case. Finally, more experiments and
analysis proved that 1) SceneRejector is a working rejector and validates the concept of feature-based
rejectors; 2) SceneRejector creates better value as the penalty of a wrong prediction increases; 3) the
value of SceneRejector is positively correlated with the accuracy improvement; 4) there exists a positive
correlation between the ECE score of the pretrained classifier and the value of SceneRejector, meaning
SceneRejector brings better value when the pretrained classifier is not well calibrated, but more research
is needed for a comprehensive conclusion; 5) The samples rejected by SceneRejector consists of quite
a few high-confidence errors. To conclude, despite the limitations, this study managed to implement a
feature-based rejector, the performance of which is close to the assumptions and hypothesis made in
the beginning.

### License
_We encourage you to use an open license and by default the repository contains an Apache License 2.0._    

## Student project report
Please consider using the official TU Delft Latex Report template:
https://d2k0ddhflgrk1i.cloudfront.net/Websections/TU%20Delft%20Huisstijl/report_style.zip





    

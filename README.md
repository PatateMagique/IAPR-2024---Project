# IAPR - Coin Detection Challenge 2024

This repository presents the work done for the Coin Detection Challenge, project proposed in the context of the [EPFL] master course [EE-451 Image Analysis and Pattern Recognition][edu].
In the following work we will build an automatic system that counts the total value of Euros and Swiss Francs on an image.

[epfl]: https://www.epfl.ch/
[edu]: https://edu.epfl.ch/coursebook/en/image-analysis-and-pattern-recognition-EE-451

I was highly motivated throughout the project and took on the majority of the implementation work myself, including all the segmentation part, data augmentation, training, and the final inferences on the test data. The competition involved over 40 teams, each consisting of three members, and we achieved a second-place finish with an accuracy of 98.4\%. 

The dataset we are using for this work is provided by the organizers of this challenge and can be downloaded [here](https://www.kaggle.com/competitions/iapr24-coin-counter/data) (private). The dataset has to be downloaded and added locally by the user.

Running the cells of this Notebook in sequential order, will:

1) Setup the paths and load the data. 
2) Demonstrate our segmentation functions on example images.
3) Generate the train images from the train data (not activated because we annotated manually our images, so we are providing them)
4) Explore different features extraction techniques.
5) Implement and test a template matching
6) Import and configure a deep learning model.
7) Train the model, save the weights and the plots, or load pretrained weights from a local folder. (recommended option)
8) Test the model and generate the submission file.

We are providing the manually annotated images in ```train_preprocessed``` and in ```validation_preprocessed```. Please place those folders in the ```iapr24-coin-counter``` folder. The augmentation has to be done by the user to save weight for the submission (this will be done automatically when running this Notebook).

The folder ```training_results``` contains our best pretrained weights that can be directly loaded by the user to avoid retraining them. It also contains the plots obtained during the training and the related csv file used for the Kaggle submission.

Before starting, make sure the data are located as follows: 

```code
└── iapr24-coin-counter
    └── ref
        ├── ref_chf.JPG
        └── ref_eur.JPG
    └── test
        ├── L0000000.JPG
        ├── ...
        └── L0000161.JPG
    └── train
        ├── 1. neutral_bg
        ├── 2. noisy_bg
        ├── 3. hand
        ├── 4. neutral_bg_outliers
        ├── 5. noisy_bg_outliers
        └── 6. hand_outliers.csv
    └── train_preprocessed
    └── validation_preprocessed
    └── train_labels.csv
    └── sample_submission.csv
├── projet.ipynb
├── report_fig
├── requirements.txt
└── training_results
    └── b0-90.6.csv
    └── b3-96.7.csv
    └── b3-98.4.csv
```

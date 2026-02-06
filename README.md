# Automated Text Recognition with Kraken

## Description
This repository contains information and Jupyter notebooks for training models for the ATR (automated text recognition) engine [Kraken](https://kraken.re/main/index.html).

## Current Issues
none

## How to use
Clone this repository or recreate the directory structure. The notebooks can be run in JupyterHubs, GoogleColab or similar instances.

There are basically two ways of training models in Kraken: *from scratch* or *fine-tuning*. *From scratch* training means training a new model with large amounts of training data without a supporting model (or base model). *Fine-tuning* requires significantly less training data but you will need to find a pre-trained model as a base. There are no clear rules when to apply which approach but generally speaking a base model is a valid option until you have at least 10.000 words of training data for each scribal hand.

In order to train segmentation or recognition models first upload all necessary files into the respective directories:
- training data: Upload all image files and corresponding xml files containing layout information and/or transcritpions to the `data` folder in this repsoitory.
- base models: If you are fine-tuning a model, upload it as your base model (they end in `.mlmodel`) to the `data` folder as well.

The notebooks in this repo provide intructions to run command line training with Kraken. Depending on your approach (training from scratch or fine-tuning) not all commands will be required. Please follow the instructions in the notebooks.

### How to obtain models
Segmentation and recognition models for eScriptorium/Kraken are non-propietary. While this comes with a lot of advantages one downside is that there is no central place to obtain models.

One option is to search the web, check GitHub etc. Since this can be time-sonsuming, a good starting point is the zenodo repository [OCR/HTR model repository](https://zenodo.org/communities/ocr_models/records?q=&l=list&p=1&s=10&sort=newest) dedicated to Kraken models.

Models that have been trained within the Berlin-based *Regesta Imperii* transcription projects are stashed in this dedicated [Regg.F.III repository](https://gitup.uni-potsdam.de/x_fskidzun_3043/regg.f.iii-transcriptions). Please note that all of these represent various stages within transcription projects and are not "final" and reliable versions.

### Train Segmentation
*tba*

### Train Recognizer
The first line in the recognizer training notebooks will install `kraken` as well as `albumentation`. While `kraken` is the software required to perform the training, `albumentation` is a package needed for applying data augmentation. This feature is part of the proposed command line commands in this notebook and will make Kraken produce digitally altered versions of the lines in the training data in order to provide more variations for training.

The next section will prepare your training data for Kraken and also tells Kraken how to compile training, validation, and test sets out of the training data.

Depending on whether you would like to train a new model from scratch or fine-tune an existing model, the next two sections will do that. Choose the one fitting to your approach and ignore the other one.

## Notice
This is a work-in-progress. Contents of this repository may be altered at any point without prior notification.

## License and credits
The contents of this repository are licenced under the CC BY-SA 4.0 licence.
The notebooks are provided by [Frederik Skidzun](https://orcid.org/0009-0002-7712-4207) for the [*Regesta Impoerii- Regesta of Emperor Frederik III (1440-1493)*](https://ri.bbaw.de/de) of the [*Berlin-Brandenburg Academy of Sciences and Humanities (BBAW)*](https://www.bbaw.de/).

## To-do
- add segmentation notebook
- extend How-to-section
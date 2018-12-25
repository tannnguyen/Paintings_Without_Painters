# Paintings Without Painters: Artist Fingerprinting and Style Transfer
Paintings Without Painters uses Kaggle's competition [Painting by Numbers](https://www.kaggle.com/c/painter-by-numbers) dataset to accomplish two tasks:
* Artist Fingerprinting: Detect whether two paintings share the same painters
* Style Transfer: Generate new paintings by applying another style on paintings of certain styles.

We have also shared [our reports]() for more detailed explanation.

## Dataset and Preprocessing
Painter By Numbers dataset provides paintings with various size; therefore, we want to regularize the model input. First we want to scale the shorter side to 256 pixels and then crop the other side to make it 256x256 pixels. As we do comparisons for different models in Artist Fingerprinting and different methods in Style Transfer, we generated the same set of training, validation, and testing dataset. Example of these datasets are in [dataset_csv]() and the generating script is in [Util]() Jupyter Notebook. 

For Artist Fingerprinting, we trained on 120,000 pairs, validation on 3,000 pairs and test on 30,000 pairs. We also make sure that the code generates a somewhat balanced dataset. For CycleGAN in Style Transfer, we used 1,000 paintings for training and 50 for testing. 

## Artist Fingerpriting
For Artist Fingerprinting, we use a Siamese architecture. We want to compare three different models within the architecture: AlexNet, VGG16, and ResNet18, running 10 epochs on Google Cloud Ubuntu 16.04 LTS with NVDIA Tesla K80 GPU Accelerator. Here are the results:

Please refer to our [code]() for more details of the architecture and our report for analysis.  

## Style Transfer
### Neural Style Transfer with CNN



### CycleGAN


## Authors
* Tan Nguyen
* Ziyan Jiang
* Morgan Hobson

## Resources

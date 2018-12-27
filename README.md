# Paintings Without Painters: Artist Fingerprinting and Style Transfer
Paintings Without Painters uses Kaggle's competition [Painting by Numbers](https://www.kaggle.com/c/painter-by-numbers) dataset to accomplish two tasks:
* Artist Fingerprinting: Detect whether two paintings share the same painters
* Style Transfer: Generate new paintings by applying another style on paintings of certain styles.

We have also shared [our reports](https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/Painting_by_Numbers.pdf) for more detailed explanation.

## Dataset and Preprocessing
Paintings By Numbers dataset provides paintings with various size; therefore, we want to regularize the model input. First we want to scale the shorter side to 256 pixels and then crop the other side to make it 256x256 pixels. As we do comparisons for different models in Artist Fingerprinting and different methods in Style Transfer, we generated the same set of training, validation, and testing dataset. Examples of these datasets are in [dataset_csv](https://github.com/tannnguyen/Paintings_Without_Painters/tree/master/dataset_csv) and the generating script is in [Util](https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/code/Util.ipynb) Jupyter Notebook. 

For Artist Fingerprinting, we trained on 120,000 pairs, validation on 3,000 pairs and test on 30,000 pairs. We also make sure that the code generates a somewhat balanced dataset. For CycleGAN in Style Transfer, we used 1,000 paintings for training and 50 for testing. 

## Artist Fingerpriting
For Artist Fingerprinting, we use a Siamese architecture. We want to compare three different models within the architecture: AlexNet, VGG16, and ResNet18, running 10 epochs on Google Cloud Ubuntu 16.04 LTS with NVDIA Tesla K80 GPU Accelerator. Here are the results:
<p>
<img src="https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/result/siamese.png">
</p>

Please refer to our [code](https://github.com/tannnguyen/Paintings_Without_Painters/tree/master/code) for more details of the architecture and our report for analysis.  

## Style Transfer
### Neural Style Transfer with CNN
Applying image-to-image style transfer using CNN with one image as content and the other image as style like described in the [paper](), we get the result:
<p>
<img src="https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/result/img2img.jpg">
</p>

### CycleGAN
Another approach that we can use is [CycleGAN]() where we train on two collections instead of just two images. We get the result as follows:

For transferring from style Art Nouveau to Romanticism:
<p>
<img src="https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/result/romanticism.png">
</p>

For transferring from style Romanticism to Art Nouveau:
<p>
<img src="https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/result/romanticism.png">
</p>

### Comparison between the two
Running both methods, we have the comparison:
<p>
<img src="https://github.com/tannnguyen/Paintings_Without_Painters/blob/master/result/comparison.png">
</p>

## Authors
* Tan Nguyen
* Ziyan Jiang
* Morgan Hobson

## Resources

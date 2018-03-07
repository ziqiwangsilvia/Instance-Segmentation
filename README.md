# Instance-Segmentation with discriminative loss function (Pytorch)

This work reproduces the method [Semantic Instance Segmentation with a Discriminative Loss Function](https://arxiv.org/abs/1708.02551) in Pytorch.
It is tailored for the [Cityscapes](https://www.cityscapes-dataset.com/) dataset. So it is a multi-class implementation, different from [CVPPP](https://www.plant-phenotyping.org/CVPPP2017-challenge).<br>
Original code is implemented in [Torch](https://github.com/DavyNeven/fastSceneUnderstanding), thanks for the contribution of Davy.<br><br>
References:<br>
[Fast Scene Understanding for Autonomous Driving](https://arxiv.org/abs/1708.02550)<br>
[Semantic Instance Segmentation with a Discriminative Loss Function](https://arxiv.org/abs/1708.02551)
## Required Installation
* Python 2.7
* Pytorch 0.3.0
* CUDA + cuDNN enabled GPU
## Dataset
* [Cityscapes](https://www.cityscapes-dataset.com/)
* [Cityscapes scripts](https://github.com/mcordts/cityscapesScripts)<br><br>
Go to Cityscapes download page and download the first four datasets. Extract the datasets into one folder and name it as "cityscapes".<br>
Downnload the cityscapes scripts, run `createTrainIdLabelImgs.py` and `createTrainIdInstanceImgs.py` to generate training labels. The output dimensions of one image mask shold be 1 x num_classes x height x width. <br>
`Notice`: Training labels are only used to make the training easier. You should adapt the predicted labels back to its original form for evaluation. 
## Code Structure
* `cityscapes.py`<br>
Prepare the training and validation datasets.
* `main.py`<br>
This scipt contains both training and validation process. However, validation part has not been tested for accuracy.
Now it focuses on visulizing the clustering results. So one or two images can be tested to check the performance. 
* `loss_function.py`<br>
Implementation of the discriminative loss function.
* `clustering.py`<br>
Implementation of post-processing part. 
* `misc.py`
* `utils.py`

## Results

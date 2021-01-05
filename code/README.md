# VDSR-Tensorflow (2018/08/14)

## Introduction
We implement a tensorflow model for ["Accurate Image Super-Resolution Using Very Deep Convolutional Networks", CVPR 16'](http://cv.snu.ac.kr/research/VDSR/VDSR_CVPR2016.pdf).
- [The author's project page](http://cv.snu.ac.kr/research/VDSR/)
- We use 291 dataset as training dataset.

## Environment
- Ubuntu 16.04
- Python 3.5

## Depenency
- Numpy
- Opencv2
- matplotlib

## Files
- main.py : Execute train.py and pass the default value.
- vdsr.py : VDSR model definition.
- train.py : Train the VDSR model and represent the test set performance.
- demo.py : Test the VDSR model and show result images and psnr.
- util.py : Utility functions for this project.
- log.txt : The log of training process.
- model : The save files of the trained VDSR.

## How to use
### Pre-processing

#### You should put the images of the 291 dataset into the '291' directory in the 'data' directory.
#### Step 1
```shell
# !!!IMPORTANT!!!
# You should execute aug_train.m and aug_test.m in 'data' directory.
# Recommend 'Octave' platform to execute matlab code '.m' 

aug_train.m 
aug_test.m

```
#### Step 2 (Final)
##### You should execute preprocess.py in 'data' directory.
```shell
python preprocess.py
```
### Training
```shell
python main.py

# if you want to change training epoch ex) 80 epoch (default) -> 120 epoch
python main.py --training_epoch 120
```

### Test
```shell
python demo.py

# default args: image_index = 1, scale = 2, coordinate = [50,50], interval = 30 
# you can change args: image_index = 13, scale = 4, coorindate [100,100], interval = 50

python demo.py --image_index 13 --scale 4 --coordinate [100,100] --interval 50
```

## Result 
##### Results on Set 5
##### PSNR on RGB space

|  Scale    | Bicubic | tf_VDSR |
|:---------:|:-------:|:----:|
| 2x - PSNR|   31.41 |   33.15 |

##### Results on Urban 100 (visual)
- Original (Urban100 / index 1)

  ![Imgur](https://github.com/DevKiHyun/VDSR-Tensorflow/blob/master/VDSR/result/original.png)
 
 - Bicubic (Urban100 / index 1)

    ![Imgur](https://github.com/DevKiHyun/VDSR-Tensorflow/blob/master/VDSR/result/bicubic.png)
 
 - VDSR (Urban100 / index 1)
 
    ![Imgur](https://github.com/DevKiHyun/VDSR-Tensorflow/blob/master/VDSR/result/VDSR.png)

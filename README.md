# CS_T0828_HW4
Single Image Super resolution using 291 dataset

## Content

- [Introduction](#introduction)
- [Methodology](#methodology)
- [Results](#results)
- [Reference](#reference)

## Introduction
This homework requires to train a model to perform super resolution on given image.

The given training dataset contains 291 images with different size.

And the testing images are from Set14 shrinked to 1/3 of their original scale.

The baseline was originally PSNR = 29.77 and modify to PSNR = 25.03.

## Methodology
Here I modify the code from <a>VDSR-Tensorflow<a href="#[1]"> [1] </a>

No architecture change, only some misimport modification and tenforflow version adaption.

Follow the instruction of the readme in the repo.

Run the data augmentation code in the repo by octave and generate about 220000 patches.

And run training for 30 epochs(I tried to train for 80 epochs, however the result is not better)

Training using tf-gpu==2.2.0 on RTX 2080ti

Other details can refer to the original repo and the code.

## Results
Can only achieve PSNR = 25.161 according to TA's evaluation

Some results with obvious difference:

Bicubic 

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/08_bic.png" width="50%" height="50%"/>

VDSR

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/08.png" width="50%" height="50%"/>

Bicubic

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/09_bic.png" width="50%" height="50%"/>

VDSR

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/09.png" width="50%" height="50%"/>

Bicubic

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/11_bic.png" width="30%" height="30%"/>

VDSR

<img src="https://github.com/PinJui/CS_T0828_HW4/blob/main/result/11.png" width="30%" height="30%"/>

## Reference
<a name="[1]"> [1] [VDSR-Tensorflow](https://github.com/DevKiHyun/VDSR-Tensorflow)

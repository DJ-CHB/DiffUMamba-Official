# Differential UMamba 

This is the official repository of Differential UMamba. It is accepted at miccai-25. The paper is available in [arxiv](). 


* This repository is based on [UMamba_Bot](https://github.com/bowang-lab/U-Mamba).
* The code is written based on the [nnUNet](https://github.com/MIC-DKFZ/nnUNet) framework.
* To train this network on your custom dataset, refer to [training](training.md).

## Model Description

<img src="./Images/diffumamba.png" alt="DiffUMamba" width="600">

- DiffUMamba targets the overfitting spurious noise learnt due to limited data setting. 
- Noise Reduction Module (NRM) is proposed to remove the common-mode noise from each of the encoder layers. 
- Inspired by the [Differential Transformer](https://openreview.net/forum?id=OvoCm1gGhN).
- DiffUMamba works well for ($<500$ volumes).

## NRM Importance

<img src="./Images/nrm-imp.png" alt="NRM Importance" width="600">
a. It illustrates the
Pearson correlation between m1 and m2 in 1,280 patches from test set processed
by the Diff-UMamba encoder. The results show low correlation
between the two embedding types.

b. Diff-UMamba adapts more effectively than UMamba-Bot to noise injection. 

## Results 
<img src="./Images/table-internal.png" alt="Internal Dataset" width="600">

* The table shows the results on the internal dataset.
* DiffUMamba outperforms state-of-the-art methods on the internal dataset.

<img src="./Images/table-brats.png" alt="BRaTS-21" width="600">

* The table shows the results on the BRaTS-21 dataset.
* DiffUMamba outperforms state-of-the-art methods on the BRaTS-21 dataset with limited data setting i.e. 16\% and 32\% of the training data.

## Visual Comparison

* The visual comparison of the segmentation results of DiffUMamba and UMamba-Bot on the internal/BraTS-21 dataset is shown below.
<img src="./Images/visual-comp.png" alt="Visual Comparison" width="600">
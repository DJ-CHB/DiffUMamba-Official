## Installation 

Requirements: `Ubuntu 20.04`, `CUDA 11.8`

1. Create a virtual environment: `conda create -n diffumamba python=3.10 -y` and `conda activate diffumamba`
2. Install [Pytorch](https://pytorch.org/get-started/previous-versions/#linux-and-windows-4) 2.0.1: `pip install torch==2.0.1 torchvision==0.15.2 --index-url https://download.pytorch.org/whl/cu118`
3. Install [Mamba](https://github.com/state-spaces/mamba): `pip install causal-conv1d>=1.2.0` and `pip install mamba-ssm --no-cache-dir`
4. Download code: `git clone `
5. `cd DiffUMamba/` and run `pip install -e`

sanity test: Enter python command-line interface and run

```bash
import torch
import mamba_ssm
```

## Data Preparation
Diff-UMamaba is built on the popular [UMamba_Bot](https://github.com/bowang-lab/U-Mamba/blob/main/umamba/nnunetv2/nets/UMambaBot_3d.py) which is based on the [nnU-Net](https://github.com/MIC-DKFZ/nnUNet) framework. If you want to train Diff-UMamba on your own dataset, please follow this [guideline](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/dataset_format.md) to prepare the dataset. 

## Train 3d Models

- Train 3D `Diff-UMamba` model

```bash
nnUNetv2_train DATASET_ID 3d_fullres all -tr nnUNetTrainerDiffUMamba 
```
## Inference

- Predict testing cases with `Diff-UMamba` model

```bash
nnUNetv2_predict -i INPUT_FOLDER -o OUTPUT_FOLDER -d DATASET_ID -c CONFIGURATION -f all -tr nnUNetTrainerDiffUMamba --disable_tta
```

- Predict testing cases with `Diff-UMamba` model

```bash
nnUNetv2_predict -i INPUT_FOLDER -o OUTPUT_FOLDER -d DATASET_ID -c CONFIGURATION -f all -tr nnUNetTrainerDiffUMamba --disable_tta
```

## Remarks

Please set the path variables `nnUNet_raw`, `nnUNet_preprocessed`, and `nnUNet_results` to your own paths.

## Paper

```
https://arxiv.org/pdf/2507.18177
```

# Bibtex Citatiom

@misc{diffumamba,
      title={Differential-UMamba: Rethinking Tumor Segmentation Under Limited Data Scenarios}, 
      author={Dhruv Jain and Romain Modzelewski and Romain Herault and Clement Chatelain and Eva Torfeh and Sebastien Thureau},
      year={2025},
      eprint={2507.18177},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2507.18177}, 
}

## Acknowledgements

This work was supported by the MINMACS Région Normandie
excellence label and ANR LabCom L-Lisa ANR-20-LCV1-0009. We thank our colleagues at CRIANN for providing us with the computational resources necessary for
this project. 


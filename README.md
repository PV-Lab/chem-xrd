![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

# Chem-XRD

**Title: Multimodal transformers with chemical priors improve the accuracy of phase classification from X-ray diffraction spectra**

![alt text](https://github.com/PV-Lab/chem-xrd/blob/main/figure/Schematic.png?raw=true)

## Table of Contents

- [1. System requirements](#1.-system-requirements)
- [2. Installation](#2.-installation)
- [3. Usage](#3.-usage)

## 1. System requirements

### 1.1 Software dependencies
- Python	3.8.18 / 3.11.8
- Pytorch 1.13.1
- numpy	1.24.3
- xrayutilities	1.7.4 / 1.7.8
- pymatgen	2023.8.10
- transformers 4.44.2
- scikit-learn 1.3.2
- scipy 1.10.1

### 1.2 Tested enviornment
- Windows 11, version 23H2
- NVIDIA GeForce GTX 3080/4090

## 2. Installation (10-15 min)

### 2.1 Install Anaconda
https://docs.anaconda.com/anaconda/install/

### 2.2 Create and activate new enviornment in anaconda prompt
```bash
conda create -n chem_xrd python=3.8.18
```
```bash
conda activate chem_xrd
```
### 2.3 Install dependencies through pip
```bash
pip install numpy==1.24.3
pip install xrayutilities==1.7.4
pip install pymatgen==2023.8.10
pip install transformers==4.44.2
pip install scikit-learn==1.3.2
```

### 2.4 Setting up Pytorch
Option 1: to install the CPU version on Linux and Windows
```bash
pip install torch==1.13.1+cpu torchvision==0.14.1+cpu torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cpu
```
Option 2: to install the GPU version (with CUDA==11.x and cuDNN>=8.5.0)
```bash
pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117
```
See also: https://pytorch.org/get-started/previous-versions/

## 3. Usage

Before use, download the XRD dataset and pretrained models at https://drive.google.com/file/d/1vBlm35L_PZZ6wtZlvAe_E2jjcrLlXTob, and place the contents in the "cif" and "pretrained_model" directories, respectively.

### 3.1 Dataset preprocessing (30-60 min, skippable)
Run [Preprocess.ipynb](Preprocess.ipynb).
The notebook shows the generation of new alloyed CIF files, the application of lattice strains, and the process of dataset generation.
For the CIF selection process, refer to [ICSD_down_selection.xlsx](ICSD_down_selection.xlsx) for further information.

### 3.2 Model training (2 days, skippable)
Run [Train.ipynb](Train.ipynb).
The notebook shows model training for both single-phase and multi-phase scenarios. In single-phase classification, the model predicts only the material ID. In multi-phase classification, the model predicts both the material ID(s) and the number of phases present.

### 3.3 Model testing (15 min)
Run [Evaluation.ipynb](Evaluation.ipynb).
The notebook shows single-phase and multi-phase classifications with Chem-XRD models on simulated and experimental datasets, reproducing figures in the main text.

### 3.4 Visualization and interpretation (5 min)
Run [Interpretation.ipynb](Interpretation.ipynb).
The notebook includes t-SNE visualizations of the training datasets, as well as interpretations of the elemental and structural contributions in the Chem-XRD models, reproducing figures in the main text and the Supplementary Information (SI).
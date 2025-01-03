![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

# Chem-XRD

![alt text](https://github.com/PV-Lab/chem-xrd/blob/main/figure/Schematic.png?raw=true)

## Table of Contents

- [System requirements](#system-requirements)
- [Installation](#installation)
- [License](#license)

## System requirements

### Software dependencies
- Python	3.8.18 / 3.11.8
- Pytorch 1.13.1
- numpy	1.24.3
- xrayutilities	1.7.4 / 1.7.8
- pymatgen	2023.8.10
- transformers 4.44.2
- scikit-learn 1.3.2
- scipy 1.10.1

### Tested enviornment
- Windows 11, version 23H2
- NVIDIA GeForce GTX 3080/4090

## Installation

### Install Anaconda (15-30 min)
https://docs.anaconda.com/anaconda/install/

### Create and activate new enviornment in anaconda prompt (5-10 min)
```bash
conda create -n chem_xrd python=3.8.18
```
```bash
conda activate chem_xrd
```
### Install dependencies through pip
```bash
pip install numpy==1.24.3
pip install xrayutilities==1.7.4
pip install pymatgen==2023.8.10
pip install transformers==4.44.2
pip install scikit-learn==1.3.2
pip install scikit-learn==1.10.1
```

### Setting up Pytorch
Option 1: to install the CPU version on Linux and Windows
```bash
pip install torch==1.13.1+cpu torchvision==0.14.1+cpu torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cpu
```
Option 2: to install the GPU version (with CUDA==11.x and cuDNN>=8.5.0)
```bash
pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117
```
See also: https://pytorch.org/get-started/previous-versions/

## License

[Creative Commons Attribution-NonCommercial (CC BY-NC 4.0)]
https://creativecommons.org/licenses/by-nc/4.0/
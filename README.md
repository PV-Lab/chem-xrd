![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)

# XRD-ViT-Chem

### Dependency
- Python	3.8.18 (KJ) / 3.11.8 (FS)
- Pytorch 1.13.1 (KJ)
- numpy	1.24.3 (KJ,FS)
- xrayutilities	1.7.4 (KJ) / 1.7.8 (FS)
- pymatgen	2023.8.10 (KJ)
- transformers 4.44.2 (KJ)
- scikit-learn 1.3.2 (KJ)

## Goal
- Natural language (text embedding) + XRD raw data (XRD embedding)
- Text embedding -> elements/expected compound (input prior), sparse coding
- XRD embedding -> 1d or 2d (nx1) embedding, continuous

## Dataset
### New cif for mix A/B/X perovskite
- [x] Data collection (Cs/FA/MA, Pb/Sn, Cl/Br/I)
- [x] Combination search
- [x] Mixed cif generation, step size 20% across composition gradient

### Preprocess
- [x] Lattice strain between -0.002~+0.002 for a, b, c; Step size 0.001
- [x] Label 1 - Element (EDS) or precursor label (e.g. MA Cs Pb Br as text input)
- [x] Label 2 - Chemical formula (e.g. gamma-CsPbI3 as formal phase name)
- [x] Dataset creation (save/load) for i) new cif and ii) ICSD

### Impurity and substrate study
- [ ] Data collection: target material, potential impurities or substrates, corresponding ICSD for all materials, references

### Dataloader
- [x] Expand from nonzero to full range XRD
- [x] Preferred orientation
- [x] Random peak intensity
- [x] Random crystal size
- [x] Random strain
- [x] Mixing of compounds, with random ratio
- [x] Background noise

## Training
- [x] Precursor (text input)
- [x] Visual embedding dim + sequence length (Visual input)
- [x] Multi-class multi-labels (output)
- [x] Loss: CrossEntropyLoss (single-label); BCEWithLogitsLoss (multi-label)

## Evaluation
- [x] Output: class label + probability (multi-label classification) -> natural language description
- [x] Confusion matrix
- [x] Top5 accuracy (precision recall F1)
- [x] XRD-XRD self attention
- [x] Precursor-XRD self attention
- [x] Precursor-Precursor self attention
- [x] Compare: No prior / EDS prior / precursor prior

## Extra / bonus
- [ ] Various data range

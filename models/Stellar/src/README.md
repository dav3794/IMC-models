# Stellar for IMC

This code was extracted from [this repository](https://github.com/D4L-Pigeons/Deep4Life). All the credits to its authors.

## Installation

We recommend creating ```venv``` or ```conda``` environment with ```python>=3.9```. 
You can use ```environment.yaml```.

### Conda and requirements.txt

```bash
conda create -n stellar python=3.9
source activate stellar
```

And then:
```bash
pip3 install -r requirements.txt
```

## Overview
When you want to run any experiment, run:

```bash
python3 train_and_validate.py [ARGUMENTS]
```

with possible options:
  * ```-h, --help```: show this help message and exit
  * ```--dataset-path``` (default="data/train"): dataset path
  * ```--method``` {stellar,torch_mlp,sklearn_mlp,xgboost} (default="stellar"): 
  * ```--config``` (default="standard"): Name of a configuration in src/config/{method} directory.
  * ```--cv-seed``` (default=42): Seed used to make k folds for cross validation.
  * ```--test``` (default=False) Test mode.
  * ```--n-folds``` (default=5): Number of folds in cross validation.
  * ```--retrain``` (default=True): Retrain a model using the whole dataset.
  * ```--model-path``` (default=None) Path to a saved model to load for inference.
  

We recommend using ```--config``` flag. Sample configs are given in ```src/config/{method}``` folders.


## Stellar

Originally STELLAR was developed by [Snap Stanford](http://snap.stanford.edu/stellar).

PyTorch implementation of STELLAR, a geometric deep learning tool for cell-type discovery and identification in spatially resolved single-cell datasets. STELLAR takes as input annotated reference spatial single-cell dataset in which cells are assigned to their cell types, and unannotated spatial dataset in which cell types are unknown. STELLAR then generates annotations for the unannotated dataset. For a detailed description of the algorithm, please see our manuscript [Annotation of Spatially Resolved Single-cell Data with STELLAR](https://www.biorxiv.org/content/10.1101/2021.11.24.469947v2.full.pdf).


<p align="center">
<img src="https://github.com/snap-stanford/stellar/blob/main/images/stellar_overview.png" width="1100" align="center">
</p>

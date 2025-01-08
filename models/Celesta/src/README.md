# Celesta for IMC

That code was extracted from [this repository](https://github.com/wtrawinska/Deep_learning_project.git). All the credits to its authors.

## Setting up
### python env
Create conda environment from `env.yaml`. 

### R env
Since CELESTA is an R package you need to also install R and some of its packages, namely: 
- CELESTA, 
- Rmixmod, 
- spdep, 
- ggplot2, 
- reshape2,  
- zeallot 

Running the script `install_packages.R` should install those packages, given all the dependencies outside R are met.


## CELESTA

CELESTA needs two inputs: 
1. Handcrafted marker expression signature file
2. CSV file with expression levels for each cell.

We provide the marker expression signature file, and the CSV files are exported from `.h5ad` file. 

For running CELESTA one needs to run `celesta.py`

``` 
usage: celesta.py [-h] anndata input_dir marker_info_path output_dir

Prepares input suitable for CELESTA based on h5ad file splitting data it into csv files corresponding to pictures
and ROI, as celesta uses X and Y information). Runs celesta and merges the outputs - merged output will be in the
output directory in the file named 'merged_celesta_output.csv'.

positional arguments:
  anndata           path to h5ad file
  input_dir         path to the directory csv files (celesta inputs) will be written to
  marker_info_path  path to csv file with prior marker info (celesta input)
  output_dir        path to the directory celesta output files will be written to

options:
  -h, --help        show this help message and exit

```
Usage example:
```
python3 celesta.py cell_data.h5ad data/celesta_input_final final_signature.csv celesta_out
```

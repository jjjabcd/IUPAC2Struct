# IUPAC2Struct model 

This is Transformer-based IUPAC2Struct model. It converts IUPAC names to SMILES strings. The model's quality is almost on the same level as rules-based OPSIN; however, our solution is purely neural one.  

| Model      | Accuracy |
| ----------- | ----------- |
| OPSIN       | 99.4%       |
| IUPAC2Struct  | 99.1%        | 

## Usage

### 1. Create the environment first:

```bash
conda env create -f environment.yml
conda activate iupac2struct
```

### 2. [Optional] Install Git LFS
If you want to use the pretrained model, you need to install [Git LFS](https://git-lfs.com/)
:
```bash
# Option A: via conda
conda install -c conda-forge git-lfs

# Option B: via apt (Ubuntu/Debian)
sudo apt-get update
sudo apt-get install git-lfs
```

### 3. Download model files:

```bash 
git lfs pull
```

### 4. Run the script:

```bash
python run.py -f {file_path} -r {number of data} -b {beam size}
```
- `-f`: path to the dataset file(CSV with input(iupac), target(SMILES))
- `-r`: number of random samples to evaluate (default: 1000)
- `-b`: beam size for the Transformer decoder (default: 5)


## Citation
Please, cite: 

_Krasnov, L., Khokhlov, I., Fedorov, M.V., Sosnin, S. Transformer-based artificial neural networks for the conversion between chemical notations. Sci Rep 11, 14798 (2021). https://doi.org/10.1038/s41598-021-94082-y_

````
@article{Krasnov2021,
  doi = {10.1038/s41598-021-94082-y},
  url = {https://doi.org/10.1038/s41598-021-94082-y},
  year = {2021},
  month = jul,
  publisher = {Springer Science and Business Media {LLC}},
  volume = {11},
  number = {1},
  author = {Lev Krasnov and Ivan Khokhlov and Maxim V. Fedorov and Sergey Sosnin},
  title = {Transformer-based artificial neural networks for the conversion between chemical notations},
  journal = {Scientific Reports}
}

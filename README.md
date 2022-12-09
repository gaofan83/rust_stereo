[![GitHub Downloads](https://img.shields.io/github/downloads/gaofan83/rust_stereo/total.svg?style=social&logo=github&label=Download)](https://github.com/gaofan83/rust_stereo/releases)


### rust_stereo: a data processing pipeline to generate annotated spatial images from Stereo-seq nanoball gene matrix data
#####
#####
### Installation
1) Download the latest version from https://github.com/gaofan83/rust_stereo/releases to Ubuntu workstation
```
wget https://github.com/gaofan83/rust_stereo/releases/download/rust_stereo_v1.0/rust_stereo
chmod 755 rust_stereo
```

### USAGE
```
Command: rust_stereo --in input.tissue.gem.gz --marker marker_genes.csv --radius 100

USAGE:
    rust_stereo [OPTIONS]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
        --in <gemin>             Please input gem.gz file
        --marker <markerin>      cell type marker gene list
        --radius <radius_bin>    radius distance (bin) for neighbour selection

######################################################################################
```
#####
### Input format
##### GEM gene count matrix
| geneID | x   | y   | MIDCount | ExonCount |
|--------|-----|-----|----------|-----------|

##### Cell marker gene list (2 column csv file with each line ends with comma)
```
Gene,Celltype,
Grin1,eNEU1,
Syt1,eNEU1,
Rbfox3,eNEU1,
Snap25,eNEU1,
Grin2a,eNEU1,
Slc17a7,eNEU1,
Satb2,eNEU1,
Gad1,iNEU1,
Gad2,iNEU1,
```
#####
### Output files
* xxx_celltypes_CELLTYPE1_UMI_full.png Celltype annotated nanoball RGB images
* xxx_cell_counts.txt Summary of celltype annotated nanoball counts
* xxx_markers.gem Gem file with nanoballs annotated by celltype
* xxx_neighbours.txt Nanoball neighbour counts 
| geneID | x   | y   | MIDCount | ExonCount |
|--------|-----|-----|----------|-----------|
#####
### Demo run
#### 1) Download adult mouse brain Stereo-seq gem data file (445Mb size) from STOMICS Database 
`wget https://ftp.cngb.org/pub/SciRAID/stomics/STDS0000058/Bin1_matrix/Mouse_brain_Adult_GEM_bin1.tsv.gz`
##### Note: the latest Stereo-seq gem file has a different file extension that ends in gem.gz
#####
#### 2) Download marker_genes_5XFAD.csv from this repo https://github.com/gaofan83/rust_stereo/
#####
#### 3) Run the following command to generate cell-type-specific image files and return statistics results
##### Result files can be downloaded from [Google Drive](https://drive.google.com/drive/folders/10LF7JoX_0CqqfQoR7xSZQqvL_9zIJA49?usp=sharing) 
```
./rust_stereo --in Mouse_brain_Adult_GEM_bin1.tsv.gz --marker marker_genes_5XFAD.csv --radius 100
```
#####

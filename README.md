[![GitHub Downloads](https://img.shields.io/github/downloads/gaofan83/rust_stereo/total.svg?style=social&logo=github&label=Download)](https://github.com/gaofan83/rust_stereo/releases)


### rust_stereo: a data processing pipeline to generate spatial images (24000x24000 RGB format) from Stereo-seq nanoball gene matrix data
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

#### Demo run
#### 1) Download adult mouse brain Stereo-seq gem data file (445Mb size) from STOMICS Database 
`wget https://ftp.cngb.org/pub/SciRAID/stomics/STDS0000058/Bin1_matrix/Mouse_brain_Adult_GEM_bin1.tsv.gz`
##### Note: the latest Stereo-seq gem file has a different file extension that ends in gem.gz
#####
#### 2) Download marker_genes_5XFAD.csv from this repo https://github.com/gaofan83/rust_stereo/
#####
#### 3) Run the following command to generate cell-type-specific image files and return statistics results
```
./rust_stereo --in Mouse_brain_Adult_GEM_bin1.tsv.gz --marker marker_genes_5XFAD.csv --radius 100
```
#####

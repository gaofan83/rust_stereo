[![GitHub Downloads](https://img.shields.io/github/downloads/gaofan83/rust_stereo/total.svg?style=social&logo=github&label=Download)](https://github.com/gaofan83/rust_stereo/releases)


### rust_stereo: a Stereo-seq data processing pipeline.
#####
#####
### Installation
1) Download the latest version from https://github.com/gaofan83/rust_stereo/releases
```
wget https://github.com/gaofan83/rust_stereo/releases/download/v1.1.0/scATAK_v1.1.0.tar.gz
tar -xvzf scATAK_v1.1.0.tar.gz
chmod +x scATAK/scATAK
```

2) Add `export SCATAK_HOME=/PATH_TO_scATAK/` to `.bashrc` file, and then `source .bashrc`.  

### USAGE
```
$SCATAK_HOME/scATAK -h

######################################################################################

scATAK [options]
-module=quant [please choose 'quant' for single-cell quantification, 'track' for group bigwig track generation, 'hic' for HiC related analysis]
Please specify the following options:
-id --sample_id=sample_sheet.csv [a sample information sheet for fastq files, must be csv format]
-genome --genome_fasta=Mus_musculus.GRCm38.dna_rm.primary_assembly.fa [ENSEMBL genome fasta file for the organism of your interest]
-gene --gene_gtf=Mus_musculus.GRCm38.101.chr.gtf [ENSEMBL gene gtf file for the organism of your interest]
-bc --blen=16 [length of cell barcode, default:16]
-bf --flen=40 [length of biological feature, should not be longer than R2 read length, default:40]
-bg --bc_group=bc_group.txt [a two-column text file with Barcode and Group. First line should be 'Barcode' and 'Group'] (for -module=track or -module=hic
-bam --bam_file=peak_calling/sampleX.bam [scATAK quant mapped bam file for sampleX] (for -module=track only)
-hic --hic_bedpe=sample_significant.bedpe [hic interaction bedpe file] (for -module=hic only)
-bin --hic_binsize=10000 [hic interaction bin size, default 10kb] (for -module=hic only)
-mtxdir --region_mtxdir=atac_regions/atac_sampleX [atac region matrix directory for sampleX] (for -module=hic only)
-t --thread=8 [threads to use, default:8]
-h --help [Help information]
```

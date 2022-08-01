# Single-cell sequencing of pig spleen after ASFV infection

## System requirements

The source code was written in R and can be run on any Linux and Windows systems that support R. It was tested with R version 4.1.0. 
R packages dependencies include: Seurat (version 4.1.1),  harmony (version: 0.1.0), DESeq2 (version: 1.36.0), Rmagic (version: 2.0.3), ggplot2 (version: 3.3.6),TCSeq (version:1.20.0).


## Installation guide
Please find the installation guide of R and R packages in their home page.

- R: https://cran.r-project.org/
- Seurat: https://satijalab.org/seurat/
- harmony: https://github.com/immunogenomics/harmony 
- DESeq2: https://bioconductor.org/packages/release/bioc/html/DESeq2.html
- Rmagic: https://mirrors.sjtug.sjtu.edu.cn/cran/web/packages/Rmagic
- ggplot2: https://mirrors.sjtug.sjtu.edu.cn/cran/web/packages/ggplot2/
- TCSeq: https://www.bioconductor.org/packages/release/bioc/html/TCseq.html

The installation is usually straightforward following the guide of the packages and Bioconductor.

## Demo
- Seurat analysis includes quality control, normalization, sample aggregating, dimension reduction, clustering and visualization. The expected outputs include cell clusters, gene expression matrix and various plots for visualization (UMAP, marker gene expression). You can find the demo of standard workflow in the home page of Seurat: https://satijalab.org/seurat/vignettes.html

- harmony performs the robust, scalable, and flexible multi-dataset integration to meet four key challenges of unsupervised scRNAseq joint embedding. You can follow the demo in the homepage of harmony:  https://github.com/immunogenomics/harmony

- DESeq2 can perform differential expression analysis based on the pseudo-bulk expression profiles aggregated for each cell type. It will output the DEG list and related statistics such as FDR. You can follow the demo of Bioconductor: https://bioconductor.org/packages/release/bioc/vignettes/DESeq2/inst/doc/DESeq2.html

- Rmagic shares information across similar cells, via data diffusion, to denoise the cell count matrix and fill in missing transcripts. You can follow the demo here: https://mirrors.sjtug.sjtu.edu.cn/cran/web/packages/Rmagic

- ggplot2 is a system for declaratively creating graphics, based on The Grammar of Graphics. You can find the demo in CRAN: https://mirrors.sjtug.sjtu.edu.cn/cran/web/packages/ggplot2/

- TCSeq performs quantitative and differential analysis of epigenomic and transcriptomic time course sequencing data, clustering analysis and visualization of temporal patterns of time course data. You can find the demo in bioconductor: https://www.bioconductor.org/packages/release/bioc/html/TCseq.html

## Instructions for use

Note: the input and output files are specified in the scripts and should be carefully checked for reuse.

### `Integrate_process.r`

This script is used to integrate samples. To run the script on the real data, first prepare the cellranger output files for each sample.
For scRNA-seq data, three files will be generated by `cellranger count` (`barcodes.tsv.gz`, `features.tsv.gz`, `matrix.mtx.gz`). Put these files in a directory with corresponding sample name. 


### `celltype.r`

This script perform cell type annotation by canonical gene markers and visualization for the specific markers. 


### `Magic.r`

This script perform the algrithm of MAGIC to smooth the gene expression matrix and visualize the distribution of cells with different CD14 and CD16 status.  

### `ISG_score.r`

This script calculate the ISG scores for each sample using a list of ISG genes.


### `DEG_analysis.r`

This script performs differential expression analysis for each cell type between two conditons.

"# scRNAseq-ASFV" 

# *TO determine*

## Article information

**Title:** 
**Authors:** 
Malki Ismael1, Raphaël Corre1, Jérémy Santamaria1,Thomas Dupic1, Arnauld Sergé3, Magali Irla1* 

1 Center of Immunology of Marseille Luminy (CIML), INSERM, CNRS, Aix-Marseille-University, 13288, Marseille, France.

3 Laboratoire adhésion inflammation (LAI),Turing Centre for Living Systems, CNRS, INSERM, Aix-Marseille University, 13288, Marseille, France.

& Corresponding author: Magali Irla (Magali.Irla@inserm.fr)

**Summary:**
Thymic involution is a hallmark of aging and a major contributor to immunosenescence, leading to a progressive decline in T-cell output. This process is characterized by profound structural remodeling of the thymus, including the loss of thymic epithelial cells and the emergence of epithelial free zones. In parallel, age-associated germinal center (GC)-like structures accumulate within the thymus, although their contribution to thymic involution remains poorly understood. Here, we investigated the cellular activity and potential role of these GC-like structures during age-related thymic remodeling. We demonstrate the occurrence of class-switch recombination and plasma cell generation within these structures, suggesting their active involvement in the aging thymic microenvironment.

**DOI:**

---

---

## Overview
This repository provides all scripts and supporting resources required to reproduce the single-cell and BCR analyses presented in the manuscript. It includes the analysis code, container definitions, and detailed instructions for reproducing each computational step. Processed datasets, generated outputs, and pre-built Docker image are distributed through Zenodo.

---

## Description of the datasets

The study includes 2 folders of datasets :
Each folder include Single-cell ,HTO and BCR datas for young and aged mice (in duplicat) for both thymus and spleen as below:

* Thymus

| Dataset name | title | genotype|Tissue| 
| :--------------- |:--------------- |:-------|:-------|
| GEX_ThyB_exp1_Young_S1_R1_001	| Mus Musculus C57BL/6J Thymic B cells GEX Young forward reads (mouse age: 8 weeks) | Young |Thymus
| GEX_ThyB_exp1_Young_S1_R2_001	| Mus Musculus C57BL/6J Thymic B cells GEX Young reverse reads (mouse age: 8 weeks) | Young |Thymus
| GEX_ThyB_exp1_Aged_S2_R1_001	| Mus Musculus C57BL/6J Thymic B cells GEX Aged forward reads (mouse age: 12 months) | Aged |Thymus
| GEX_ThyB_exp1_Aged_S2_R2_001	| Mus Musculus C57BL/6J Thymic B cells GEX Aged reverse reads (mouse age: 12 months) | Aged |Thymus
| HTO_ThyB_exp1_Young_S5_R1_001	| Mus Musculus C57BL/6J Thymic B cells HTO Young forward reads (mouse age: 8 weeks) | Young |Thymus
| HTO_ThyB_exp1_Young_S5_R2_001	| Mus Musculus C57BL/6J Thymic B cells HTO Young reverse reads (mouse age: 8 weeks) | Young |Thymus
| HTO_ThyB_exp1_Aged_S6_R1_001	| Mus Musculus C57BL/6J Thymic B cells HTO Aged forward reads (mouse age: 12 months) | Aged |Thymus
| HTO_ThyB_exp1_Aged_S6_R2_001	| Mus Musculus C57BL/6J Thymic B cells HTO Aged reverse reads (mouse age: 12 months) | Aged |Thymus
| BCR_ThyB_exp1_Young_S3_R1_001	| Mus Musculus C57BL/6J Thymic B cells BCR Young forward reads (mouse age: 8 weeks) | Young |Thymus
| BCR_ThyB_exp1_Young_S3_R2_001	| Mus Musculus C57BL/6J Thymic B cells BCR Young reverse reads (mouse age: 8 weeks) | Young |Thymus
| BCR_ThyB_exp1_Aged_S4_R1_001	| Mus Musculus C57BL/6J Thymic B cells BCR Aged forward reads (mouse age: 12 months) | Aged |Thymus
| BCR_ThyB_exp1_Aged_S4_R2_001	| Mus Musculus C57BL/6J Thymic B cells BCR Aged reverse reads (mouse age: 12 months) | Aged |Thymus

* Spleen

| Dataset name | title | genotype|Tissue| 
| :--------------- |:--------------- |:-------|:-------|
| GEX_ThyB_exp1_Spleen_S1_R1_001 | Mus Musculus C57BL/6J Splenic B cells GEX forward reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
| GEX_ThyB_exp1_Spleen_S1_R2_001 | Mus Musculus C57BL/6J Splenic B cells GEX reverse reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
| HTO_ThyB_exp1_Spleen_S3_R1_001 | Mus Musculus C57BL/6J Splenic B cells HTO forward reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
| HTO_ThyB_exp1_Spleen_S3_R2_001 | Mus Musculus C57BL/6J Splenic B cells HTO reverse reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
| BCR_ThyB_exp1_Spleen_S2_R1_001 | Mus Musculus C57BL/6J Splenic B cells BCR forward reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
| BCR_ThyB_exp1_Spleen_S2_R2_001 | Mus Musculus C57BL/6J Splenic B cells BCR reverse reads (mouse age: 8 weeks and 12 months) | Young/Aged |Spleen
---

## Description of the main analysis

The computational workflow is organized into two successive stages.

### First step : Individual dataset analysis

Each dataset is first processed independently to assess sequencing quality and characterize cellular heterogeneity prior to integration.

Scripts and corresponding outputs for this stage are stored within the folder associated with each dataset.

### Second step : Merge all datasets

After quality assessment, all datasets are combined into a single integrated analysis to enable comparisons between experimental conditions and tissues.

The scripts and outputs corresponding to this integrated analysis are available in the Integrated directory.


### Third step : Global heterogeinity analysis and BCR repertoire analysis

After the integration , all the analysis steps mentioned in the article are made from this step including final UMAP , cell proportions , gene expression and BCR analysis

---

## Folders of the datasets

The repository is structured around individual datasets. Each dataset has its own directory containing the analysis resources. After downloading both the repository and associated data, the project hierarchy should resemble the following:

```
.
└── Aging_B
    ├── ThyB
    ├── SpleenB
    └── spleen_thymus_sc_merge
``` 
---

## Prepare the environments

Before running the analyses, a few setup steps are required:

* clone the GitHub repository and define the WORKING_DIR environment variable;
* Download the datasets;
* Install Snakemake
* Install Docker and Singularity to execute the analyses within the provided containerized environment.

Detailed instructions are provided below.

---

## Clone the GitHub repository

Clone the repository into the directory of your choice using your preferred Git client. This will create a local **Aging_B** directory containing all analysis scripts.

--- 

## Set the WORKING_DIR variable

Then, you must set an environment variable called **WORKING_DIR** with a value set to the path to this folder.

For instance, if you have chosen to clone the Git repository in __"/home/malki/workspace"__, then the **WORKING_DIR** variable will be set to __"/home/malki/workspace/Aging_B"__

**On linux:**

```
    export WORKING_DIR=/home/malki/workspace/Aging_B
```

---

Each dataset directory contains two complementary groups of files: one dedicated to the analysis code and another containing the generated outputs.

 * The GitHub repository provides the source code, including the scripts (03_Scripts) and Docker definition files (02_Container).
Scripts of the pre-processing steps are provided for Cell Ranger count analysis and corresponding raw data (fastq files) can be downloaded from GEO (see article).
This creates the main project directory:
```
.
└── Aging_B
    ├── ThyB
    │      └── ThyB_single_cell
    │         ├── 02_Container
    │         └── 03_Scripts
    ├── SpleenB
    │      └── SpleenB_single_cell
    │         ├── 02_Container
    │         └── 03_Scripts
    └── spleen_thymus_sc_merge
           └── spleen_thymus_sc_merge
              ├── 02_Container
              ├── 03_Scripts
              └── 04_Workflow
```

---

## Download the dataset

Once you have done this download the zenodo archives
* The Zenodo archive contains the pre-built container images, processed data and analysis outputs.
Each experiment needs its own sub-folder containing the initial data used by the analysis. Those data can be downloaded from Zenodo and uncompressed. The Zenodo dataset DOI are [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5564625.svg)](https://doi.org/10.5281/zenodo.5564625), [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5565864.svg)](https://doi.org/10.5281/zenodo.5565864) and [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5566675.svg)](https://doi.org/10.5281/zenodo.5566675). The initial data from the analysis are the pre-processed data :
To download and uncompress the data, use the following code:

**On linux:**

```
    cd $WORKING_DIR
    wget https://zenodo.org/record/5564625/files/10x_190712_m_moFluMemB_processedData.tar.gz -O ThyB.tar.gz
    tar zxvf ThyB.tar.gz
    
    wget https://zenodo.org/record/5565864/files/10x_191105_m_moFluMemB_processedData.tar.gz -O SpleenB.tar.gz
    tar zxvf SpleenB.tar.gz

    wget https://zenodo.org/record/5566675/files/custom_201216_m_moFluMemB_processedData.tar.gz -O spleen_thymus_sc_merge.tar.gz
    tar zxvf spleen_thymus_sc_merge.tar.gz
```

Once done, you may obtain the following subfolder structure, each of them containing several files.

```
.
└── Aging_B
    ├── ThyB
    │     └── ThyB_single_cell
    │           ├── 01_References
    │           ├── 02_Container
    │           ├── 03_Scripts
    │           └── 05_Output
    ├── SpleenB
    │     └── SpleenB_single_cell
    │           ├── 01_References
    │           ├── 02_Container
    │           ├── 03_Scripts
    │           └── 05_Output
    ├── spleen_thymus_sc_merge
    │     └── spleen_thymus_sc_merge
    │           ├── 01_References
    │           ├── 02_Container
    │           ├── 03_Scripts
    │           ├── 04_Workflow
    │           └── 05_Output
    
```

---

#### Add your working dir in the code

Several parameter files contain project-specific settings. In particular, each dataset includes a **projectParams.R** file located in **03_Scripts**, where the **PATH_PROJECT** variable specifies the project location.

Locate this file for each dataset and update **PATH_PROJECT** so that it matches your local **WORKING_DIR**.

For instance:

```
    AgingB
    └── ThyB
          └──ThyB_single_cell 
              └── 03_Script/projectParams.R

```

Edit those files and in each of them locate the line defining the **PATH_PROJECT** variable and change its value to the same value as the **WORKING_DIR** variable you defined before. Then save the files.

```
for example :

PATH_PROJECT = "/home/malki/workspace/AgingB"
```

---
### Install the Docker environment to run the analysis interactively

#### Install Docker and Singularity 

You need to install Singularity on your system to run the complete analysis . Follow the instructions here : https://sylabs.io/guides/2.6/admin-guide/

To execute the analyses interactively through RStudio, install Docker by following the official installation guide:

https://docs.docker.com/get-docker/


### Download the Singularity images

**spleen_thymus_sc_merge/02_Container** folder contains the Singularity images for the single-cell RNA-seq analysis. Since the Singularity images are used for the 3 single-cell analyses, they must be present in all the sample folder in the same **02_Container** subfolder. Instead of copying the image files, we will create symbolic links to spare disk space:

**On linux:**

```
    cd $WORKING_DIR/spleen_thymus_sc_merge/spleen_thymus_sc_merge/02_Container
    tar zxvf seurat_analysis.sif.tar.gz
    ln -s $WORKING_DIR/spleen_thymus_sc_merge/spleen_thymus_sc_merge/02_Container/seurat_analysis.sif $WORKING_DIR/ThyB/ThyB_single_cell/02_Container/seurat_analysis.sif
    ln -s $WORKING_DIR/spleen_thymus_sc_merge/spleen_thymus_sc_merge/02_Container/seurat_analysis.sif $WORKING_DIR/SpleenB/SpleenB_single_cell/02_Container/seurat_analysis.sif
```

### (Optional) Download the Docker images and load them on your system

**spleen_thymus_sc_merge/02_Container** folder contains the Docker images for the single-cell RNA-seq analysis.YOu only need to extract and load it one time
```
    cd $WORKING_DIR/spleen_thymus_sc_merge/spleen_thymus_sc_merge/02_Container
    tar zxvf seurat_anaylysis.tar.gz
    docker load -i seurat_anaylysis.tar
```

#### Install Snakemake

You need Snakemake to run the complete workflow , use your preferred solution

---
---

## Run the analysis

### Run the analysis workflow using Snakemake

The analysis workflow uses the Singularity images and Snakemake.

The study contains 3 analysis of single-cell RNA-seq data. Each analysis have several steps for which you will find the R script files in the subfolder **03_Script**.

Each step of analysis generates its own HTML report file and several output files. Some output files of some steps are used by other steps, making a complete workflow of analysis. The output files are stored in each datatset folder in a sub-folder named "05_Output".

The simpliest way to run the complete single-cell analysis of a sample is to use the Snakemake workflow dedicated to each sample. The workflow is controlled by a snakefile stored in the **04_Workflow** subfolder of **spleen_thymus_sc_merge** folder. This workflow uses Singularity images (see above) to control the software environment for each analysis step. So you need both Snakemake and Singularity installed on your system to use this workflow (see above).

In order to use the snakemake workflow, please type first the following commands:

To run the analysis for the three datasets, run the following commands:
```
     cd $WORKING_DIR/spleen_thymus_sc_merge/spleen_thymus_sc_merge/04_Workflow
     snakemake -r --snakefile All_analysis.py --cores (choose cores u want to use) --sdm apptainer --apptainer-args "--bind /$WORKING_DIR:/$WORKING_DIR"
```

#### Run the analysis individually using Docker

If you have loaded the docker images (see above), you can use Rstudio in Docker to run the analysis individually.

Launch the container with:

```
docker run -d -p 8787:8787 -v /$WORKING_DIR:/$WORKING_DIR -e PASSWORD=<PASSWORD> -e USER=$(whoami) -e USERID=$(id -u) -e GROUPID=$(id -g)  seurat_analysis
```

where:

* <PASSWORD> is a simple string you will use as password to login into Rstudio

Once the container is running, open a web browser and connect to:

https://127.0.0.1:8787

Authenticate using your Linux username together with the password specified above.

The RStudio session will have direct access to the mounted **WORKING_DIR** , allowing you to browse the project files and execute the analyses.

The main entry point of each workflow is the **launch_report.R** script.


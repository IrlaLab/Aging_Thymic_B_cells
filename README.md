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

## Structure of the data and code

### Folders of the datasets

The repository is structured around individual datasets. Each dataset has its own directory containing the analysis resources. After downloading both the repository and associated data, the project hierarchy should resemble the following:

```
.
└── Aging_B
    ├── ThyB
    ├── SpleenB
    └── Integrated
``` 

### Folders inside the datasets

Each dataset directory contains two complementary groups of files: one dedicated to the analysis code and another containing the generated outputs.

 * The GitHub repository provides the source code, including the scripts (03_Scripts) and Docker definition files (02_Container).
```
.
└── Aging_B
    ├── ThyB
    │   ├── 02_Container
    │   ├── 03_Scripts
```

 * The Zenodo archive contains the rawdata ,pre-built container images, processed data and analysis outputs.
 
```
.
└── Aging_B
    ├── ThyB
    │   ├── 00_RawData
    │   ├── 02_Container
    │   ├── 05_Output

```

---
---

## Prepare the environments

Before running the analyses, a few setup steps are required:

* clone the GitHub repository and define the WORKING_DIR environment variable;
* download the datasets;
* install Docker to execute the analyses within the provided containerized environment.

Detailed instructions are provided below.

---

#### Clone the GitHub repository

Clone the repository into the directory of your choice using your preferred Git client. This will create a local **Tcf7** directory containing all analysis scripts.

#### Set the Working Dir variable

Create an environment variable named **WORKING_DIR** pointing to the location of the cloned repository.

For example, if the repository was cloned into **/home/malki/workspace**, the variable should be defined as:

**On linux:**

```
    export WORKING_DIR=/home/malki/workspace/AgingB
```

#### Add your working dir in the code

Several parameter files contain project-specific settings. In particular, each dataset includes a **projectParams.R** file located in **03_Scripts**, where the **PATH_PROJECT** variable specifies the project location.

Locate this file for each dataset and update **PATH_PROJECT** so that it matches your local **WORKING_DIR**.

For instance:

```
    AgingB
    │
    ├── ThyB
    │   │
    │   └── 03_Script/projectParams.R

```

Edit those files and in each of them locate the line defining the **PATH_PROJECT** variable and change its value to the same value as the **WORKING_DIR** variable you defined before. Then save the files.

```
for example :

PATH_PROJECT = "/home/malki/workspace/AgingB"
```

---

### Download the data

Raw FASTQ sequencing files are publicly available from GEO, whereas processed datasets and analysis outputs can be obtained from Zenodo.

********ADD THE ZENODO FILES******************

To preserve the expected directory structure, extract the downloaded files directly into **WORKING_DIR**.

To download and uncompress the data, use the following code:


**On linux:**

```
    cd $WORKING_DIR
    wget https://zenodo.org/record/21217512/files/Tcf7_WT_sc.tar.gz -O Tcf7_WT_sc.tar.gz *to modify
    tar zxvf Tcf7_WT_sc.tar.gz
    
    wget https://zenodo.org/record/21395547/files/Tcf7_KO_sc.tar.gz -O Tcf7_KO_sc.tar.gz *to modify
    tar zxvf Tcf7_KO_sc.tar.gz

    wget https://zenodo.org/record/21395640/files/Tcf7_Integrated.tar.gz -O Tcf7_Integrated.tar.gz *to modify
    tar zxvf Tcf7_Integrated.tar.gz
```
 
Once done, you may obtain the following subfolder structure, each of them containing several files.

```

    AgingB
    ├── ThyB
    │   ├── 00_RawData
    │   ├── 02_Container
    │   └── 05_Output
    ├── SpleenB
    │   ├── 00_RawData
    │   ├── 02_Container
    │   └── 05_Output
    └── Integrated
        ├── 02_Container
        └── 05_Output

```

--- 

#### Download the container images

Docker archives (.tar.gz) are available in the **02_Container** directory of each dataset.

Docker archives must first be imported into your local Docker installation.

---

### Install the Docker environment to run the analysis interactively

#### Install Docker

To execute the analyses interactively through RStudio, install Docker by following the official installation guide:

https://docs.docker.com/get-docker/


#### Load the images

Once done, load the downloaded image using:

```
docker load -i <image_name>.tar.gz
```

#### Run the analysis individually using Docker

If you have loaded the docker images (see above), you can use Rstudio in Docker to run the analysis individually.

Launch the container with:

```
docker run -d -p 8787:8787 -v /$WORKING_DIR:/$WORKING_DIR -e PASSWORD=<PASSWORD> -e USER=$(whoami) -e USERID=$(id -u) -e GROUPID=$(id -g)  <IMAGE_NAME>
```

where:

* <PASSWORD> is a simple string you will use as password to login into Rstudio
* <IMAGE_NAME> is the Docker image name to run

Once the container is running, open a web browser and connect to:

https://127.0.0.1:8787

Authenticate using your Linux username together with the password specified above.

The RStudio session will have direct access to the mounted **WORKING_DIR** , allowing you to browse the project files and execute the analyses.

The main entry point of each workflow is the **launch_report.R** script.


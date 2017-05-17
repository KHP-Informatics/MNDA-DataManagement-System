![alt text](https://github.com/KHP-Informatics/MNDA-DataManagement-System/blob/master/danm_logo.001.jpeg)

# MNDA-DataAnalysis&Management-System

    This project is a collaboration between researchers working in motor neuron disease, and computer 
    scientists working with biological information. We would welcome anybody bringing up their own 
    issues, experience or suggestions. We wish the whole ALS research community to partecipate and 
    guide this project development. Please contact us via email (alfredo.iacoangeli@kcl.ac.uk) or 
    post a message in the issue blog (menu above)

## DANM system

This is the main repository of our Data ANalysis and Management (DANM) system for ALS research. Our framework aims to deal with the new challenges that ALS researchers are facing nowadays . Indeed Genetic technology is advancing rapidly. We now have the ability to quickly and cheaply collect huge amounts of genetic information, and because of close collaboration between research groups, to do this in tens of thousands of people. How to store, handle and easily share this information might represent overwhelming challenges. The aim of our DANM framework is to make all members of our research community able to deal with these aspects of our research in order to speed up our studies, make them more reliable and reproducible.
In this repository we provide instructions and tools to set up the data management and analysis framework in a few easy steps both as local deployment and as dokerized/Singularity deployment. 

**Authors:** Alfredo Iacoangeli, Richard Dobson, Stephen J Newhouse and Ammar Al-Chalabi

## Author Contact Details

Please contact us for help/guidance on using our framework.

|Author|email|Twitter| LinkedIn|
|----|----|----|----|
|Dr Alfredo Iacoangeli| <alfredo.iacoangeli@kcl.ac.uk>| 
|Dr Stephen J Newhouse| <stephen.j.newhouse@gmail.com>| [@s_j_newhouse](https://twitter.com/s_j_newhouse?lang=en)| View Steve's profile on [LinkedIn](http://uk.linkedin.com/pub/dr-stephen-newhouse/29/89a/11a)|

## Project plan

We are implementing a solution that will enable sharing, analysing and storing of each of the 1-4 levels of omics and associated data: Level 1 data refers to the data in its raw, non-normalised form, levels 2 and 3 represent data at different stages of processing and level 4 represents summary results data (https://wiki.nci.nih.gov/display/TCGA/Data+level#Datalevel- DataLevelClassification).
A number of different challenges and requirements exist when considering each level. For level 1-2 data a file system such as iRODS (Integrated Rule-Orientated Data system,https://www.irods.org/) can be used, whereas Level 3 and 4 data, along with the clinical data, will be loaded into a knowledge platform such as tranSMART(http://transmartfoundation.org). 

### Development of iRODS file storage system for level 1-2 data

iRODS is an integrated Rule-Oriented Data System, developed to build distributed storage infrastructure. Several iRODS servers in different locations can share their data through automatic mechanisms based on internal rules. But iRODS is also useful to provide users with a remote storage area supporting large files, large numbers of files and identity management. Although we propose to centralise data for this project, it provides us with the capability to build a federated system if this is preferred by the ALS stakeholder advisory group. The approach will enable us to handle diverse data types, provide controlled fine grained access controls, add/remove data/users/partners/different infrastructure. It is being widely adopted by institutes such as the BROAD Institute and Sanger Centre for managing highly dimensional data, typical of modern genomic datasets and is particularly important as these datasets are not managed well by standard relational database management systems.
iRODS allows to deal with distributed network of data repositories as the ALS research network. Throw data federation it would allow an easy data access and sharing across the international research community favouring collaborations. In this repository we provide instructions and tools to set up an iRODS data management system in a few easy steps.

We also provide a set of ALS research specific microservices/rules to allow the researcher to exploit iRODS metadata and rule engine services (work in progress)

[An iRODS data browser](https://github.com/KHP-Informatics/MNDA-DataManagement-System/tree/master/irods-cloud-browser-1.0.1-RELEASE) is available at the address http://52.202.127.9:8552/irods-cloud-frontend/ 
This browser allows to log in and explore any iRODS zone. The following credentials allow to log in into a sample iRODS zone based onto Rosalind (our King's/MRC HPC cluster) 

![alt text](https://github.com/KHP-Informatics/MNDA-DataManagement-System/blob/master/Screen.png)



### Development of TranSMART open source knowledge platform for level 3 and 4 data, with integration of clinical information

The TranSMART system is a platform for translational medicine comprising a relational database back end and a web based interface that integrates a large number of open source bioinformatics tools for analysis and visualisation, including GenePattern for expression analysis, Plink for genetic analysis, Galaxy, R and add on statistical packages (box plot with ANOVA, Fisher test, k-means clustering and others). The system, originally developed by Johnson & Johnson and based on i2b2 technology, has recently been released under an open source license and is being widely adopted and developed by the open source community. It is the tool of choice for many EU projects integrating clinical and omics datasets across Europe and beyond. This platform will provide general user access to processed data and will enable cohort selection and analyses on the fly. For example, it allows a user to select a subset of patients, filtered on clinical and phenotypic variables such as age, gender, age of onset and genotype, then perform an analysis such as a differential expression analysis, or extract a subset a selection of genotypes and visualise the results.

## Data analysis and analysis reproducibility tools

Bioinformatics is speeding up genetic research showing great prospectives. Unfortunately due to the nature of this field, its tools and pipelines often lack in maintenance effort and user friendly interfaces. This might result in performance inconsistence among different versions of the same tool and unreliable availability of "old" tools stable versions. Moreover, their use and deployment often requires informatics skills way beyond the average user. This is particularly true in a medical/biology research environment as the ALS research is. This section wants to provide tools able to automatise the deployment and use of bioinformatics pipelines. 
We aim to develop a super user friendly interface for these tools (a web server) able to interactively create, using technologies such as Docker and Singularity, stand-alone and portable deployments of bioinformatics pipelines according to the user needs. (work in progress...) 

### NGSeasy

NGSeasy is a flexible and easy-to-use NGS pipeline for automated alignment, quality control, variant calling and annotation. The pipeline allows users with minimal computational/bioinformatic skills to set up and run an NGS analysis on their own samples, in less than an afternoon, on any operating system (Windows, iOS or Linux) or infrastructure (workstation, cluster or cloud). 

https://github.com/KHP-Informatics/MNDA-DataManagement-System/tree/master/ngseasy

### bcbio

A python toolkit providing best-practice pipelines for fully automated high throughput sequencing analysis. You write a high level configuration file specifying your inputs and analysis parameters. This input drives a parallel pipeline that handles distributed execution, idempotent processing restarts and safe transactional steps. The goal is to provide a shared community resource that handles the data processing component of sequencing analysis, providing researchers with more time to focus on the downstream biology.

https://github.com/chapmanb/bcbio-nextgen

## iRODS  

The following sections will give the user a quick how-to-get-started guide for iRODS
For more complete instructions and details please read either the iRODS [manual](https://docs.irods.org/4.2.0/) or this [tutorial](https://irods.org/uploads/2016/06/irods_beginner_training_2016.pdf)

### iRODS deployment



### iRODS tutorial

### iRODS rules

### iRODS microservices

### iRODS extras

### Metadata

## tranSMART 

### tranSMART deployment

### tranSMART tutorial

### tranSMART extras

## Docker/Singularity 

### Docker deployment

### Singularity deployment

### Docker/Singularity extras

## Extras

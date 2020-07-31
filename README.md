# MetaPLMA - Metabolite Peak List Merge & Annotation Tool

![Scripting](https://img.shields.io/badge/Language-R-red.svg) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) ![Current Version](https://img.shields.io/badge/Version-v1.0-blue.svg)(Work in progress!) 

This tool is written in **R** and allows the reproducible and scalable data processing of peak information acquired trough **Gas Chromatography Mass Spectrometry (GC/MS)**. The tool bridges the gap between the output of pre-analysis software like [**Thermo Xcalibur-TraceFinder**](https://www.thermofisher.com/de/de/home/industrial/mass-spectrometry/liquid-chromatography-mass-spectrometry-lc-ms/lc-ms-software/lc-ms-data-acquisition-software/tracefinder-software.html) or [**Shimadzu GCMS solution**](https://www.ssi.shimadzu.com/products/gas-chromatography-mass-spectrometry/gcmssolution-software.html) and required input formats for downstream metabolite analysis using common tools such as [**MetaboAnalyst**](https://www.metaboanalyst.ca). 

The software is very easy to install, includes additional plotting and reporting functions and can be run on machines operating **Windows**, **Mac OS** or **Linux**. It reads in individual pre-processed GC/MS data files containing metabolite-peak data of single samples, collects additional sample information regarding dry weight and creates condensed and normalised **Compound-Concentration Matrix** outputs suitable for further downstream analysis. Up to 198 input files of the type .pdf, .tsv, .csv, .txt or .xlsx can be processed at the same time.  

<figure class="image" >
  <p align="center"> 
    <img src="https://github.com/AndreHolzer/MetaPLMA/blob/master/images/MetaPLM-workflow.png?raw=true" width="600">
    <br>
    <em><b>Fig. 1:</b> Schematic diagram displaying the individual files and steps of the tool</em>
   </p> 
</figure>

The tool can be operated using either a GUI interface, R markdown, or the command line (the latter which is still work in progress). The tool has been tested on both Mac and Windows operating systems, analysing GC/MS data obtained from different algae samples. 




### Features

- **Simplicity**: The tool provides reproducible and scalable data analysis which can be executed across operating systems.
- **Integrated data extraction from .pdf and .xlsx files of common peak quantification tools**: Starting from .pdf files the tool allows easy extraction of GC/MS summary data from common pre-processing tools such as Thermo Xcalibur-TraceFinder or Shimadzu GCMS solution.



### **Quick links:**

- Jump to [Prerequisites](https://github.com/AndreHolzer/MetaPLMA#prerequisites)
- Jump to [Installing](https://github.com/AndreHolzer/MetaPLMA#installing)
- Jump to [Usage](https://github.com/AndreHolzer/MetaPLMA#usage)
- Jump to [Support](https://github.com/AndreHolzer/MetaPLMA#support)
- Jump to [Citation](https://github.com/AndreHolzer/MetaPLMA#citation)



## Getting Started

### Prerequisites

- #### **R**

  Install the latest version of R. A full installation guide can be found on the [CRAN website](https://cran.r-project.org/). 

  Quick download links (Version 4.0.2):

   - [R for Windows](https://cran.r-project.org/bin/windows/base/R-4.0.2-win.exe)

   - [R for Mac OS High Sierra and higher](https://cran.r-project.org/bin/macosx/R-4.0.2.pkg)

   - [R for Linux](https://cran.r-project.org/bin/linux/)
  
     

- #### **RStudio**

  Install the latest version of RStudio. More information can be found [here](https://rstudio.com).

  Quick download links:

   - [RStudio for Windows](https://rstudio.com/products/rstudio/download/#download)

   - [RStudio for Mac](https://rstudio.com/products/rstudio/download/#download)

   - [RStudio for Linux](https://rstudio.com/products/rstudio/download/#download)



### Installing

**Clone/Download the repository from Github**

Get the latest version/release of the tool using the Pull or Git clone command

```
 git clone https://github.com/AndreHolzer/MetaPLMA --recursive
```

or for Windows: got to the [GitHub page](https://github.com/AndreHolzer/MetaPLMA) and download the latest release as .zip file ([Quick download](https://github.com/AndreHolzer/MetaPLMA/archive/master.zip))



### Usage

#### **Input**

The tool takes two different inputs, the GC/MS peak data (metabolite vs. peak intensity), as well as additional sample information regarding dry weights.

> **IMPORTANT**: FILE NAMES MUST NOT CONTAIN ANY SPACES

1. ##### GCMS data (required)

   GCMS data must contain information on Compounds, Response time (RT) and Peak Intensity (Response) and can be provided in several formats: 

   - `.pdf`: format from Thermo analysis output is supported and once loaded will be converted into .tsv format ([see example input](https://github.com/AndreHolzer/MetaPLMA/blob/master/example_data/input/Thermo-Xcaliber-Tracefinder/Thermo-example_output_1.pdf))
   - `.tsv`: format containing three columns (Compound, Retention time, Response) ([see example input](https://github.com/AndreHolzer/MetaPLMA/blob/master/example_data/input/Sample1.tsv))
   - `.csv`: format containing three columns (Compound, Retention time, Response) ([see example input](https://github.com/AndreHolzer/MetaPLMA/blob/master/example_data/input/Sample1.tsv))
   - `.xlsx`: format with first sheet containing three columns (Compound, Retention time, Response) or in Shimadzu output format ([see example input](https://github.com/AndreHolzer/MetaPLMA/blob/master/example_data/input/Shimadzu_GCMSsolution/1_1_fame.xlsx))

   

2. ##### Dry weights (optional)

   Dry weight information about the individual samples must be provided in a tab separate file of the following format. 

   | Sample                            | DW          | Unit                 |
   | --------------------------------- | ----------- | -------------------- |
   | \<File name including extension\> | \<integer\> | \<character string\> |
   | \<File name including extension\> | \<integer\> | \<character string\> |
   | \<File name including extension\> | \<integer\> | \<character string\> |

   > **IMPORTANT**: DO NOT USE ANY OTHER COLUMN NAMES

   Edit the [Sample_info.tsv](example_data/Sample_info.tsv) file to add specific sample dry weight conditions.



#### **Modes of execution**

- ##### Fast track (GUI interface and progress log) (<u>*coming soon*</u>)

  > **IMPORTANT**: NOT CURRENTLY SUPPORTED (WORK IN PROGRESS)

  Execute the analysis by a simple double click onto the

  - run.bat (on Windows)
  - run.sh (on Linus & Mac OS)

  

- ##### Full interactive track (GUI + progress log + full error reporting + code interaction possible)

  - Start RStudio and load/open the main analysis script ([MetaPLMA_main-anaylsis-script.R](scripts/MetaPLMA_main-anaylsis-script.R)) from the scripts folder
  - Klick Source to run the analysis

  > **IMPORTANT**: Once the analysis has finished check progress log and console to see whether there were any errors.

  

#### **Data Output**

A main output folder `<date>_GCSM-analysis-results` will be created under the select output directory which will include up to three output subfolder: `pdf2tsv` stores information that was extracted from from .pdf files (if input files where of this type), `plots` stores all plots generated, and `peak_data` stores all matrixes containing retention time and response data for all sample.

A final summary of the RT and Response data is stored in `<date>_GCSM-analysis-results/peak_data/<date>_MetaPLMA_analysis-results_retention-times_all-files.xlsx.xlsx` and `<date>_GCSM-analysis-results/peak_data/<date>_MetaPLMA_analysis-results_response-data_all-files.xlsx.xlsx` .



## Support

If you have questions or suggestions, email us at [andre.holzer.biotech@gmail.com](mailto:andre.holzer.biotech@gmail.com?subject=ATAC-Seq_pipeline), or file a [GitHub issue](https://github.com/AndreHolzer/MetaPLMA/issues). Please use issues to the GitHub repository for feature requests or bug reports.



## Citation

**If you use this pipeline for your analysis, please don't forget to cite:**

**DOI: …** (*<u>coming soon, please get in contact before using the tool</u>*)



#### **Developers**

- **Andre Holzer** - *PhD Student, Department of Plant Sciences, Univeristy of Cambridge* [https://orcid.org/0000-0003-2439-6364][https://orcid.org/0000-0003-2439-6364]

- **Matthew P Davey ** - *Senior Research Associate, Department of Plant Sciences, Univeristy of Cambridge* [https://orcid.org/0000-0002-5220-4174](https://orcid.org/0000-0002-5220-4174)

We would like to thank Monika Krolikowski for trailing the software. We'd also like to acknowledge Aom Buayam who contributed prototype some parts of this tool.


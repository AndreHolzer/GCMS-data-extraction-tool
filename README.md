# MetaPLMA - Metabolite Peak List Merge & Annotation & Polishing Tool

![Scripting](https://img.shields.io/badge/Language-R-red.svg) [![License: REASEARCH ONLY](https://img.shields.io/badge/License-RESEARCH-yellow.svg)](LICENSE) ![Current Version](https://img.shields.io/badge/Version-v1.0-blue.svg) ![DOI](https://img.shields.io/badge/DOI-...-green.svg)

MetaPLMA is a **R** tool that allows easy data processing of common **Liquid- or Gas Chromatography Mass Spectrometry (LC-/GCMS)** raw peak data. The tool bridges the gap between the output of MS-analysis software like [**Thermo Xcalibur-TraceFinder**](https://www.thermofisher.com/de/de/home/industrial/mass-spectrometry/liquid-chromatography-mass-spectrometry-lc-ms/lc-ms-software/lc-ms-data-acquisition-software/tracefinder-software.html) or [**Shimadzu GCMS solution**](https://www.ssi.shimadzu.com/products/gas-chromatography-mass-spectrometry/gcmssolution-software.html) and downstream metabolite analysis applications such as [**MetaboAnalyst**](https://www.metaboanalyst.ca). 

The software is very easy to install, includes additional plotting and reporting functions and can be run on machines operating **Windows**, **Mac OS** or **Linux** in a reporducible and scalable manner. It reads in individual pre-processed LC-/GCMS data files containing compound-peak data of single samples, collects additional sample information regarding dry weight and creates normalised and polished **Metabolite-Concentration Matrix** outputs at different levels of condensation suitable for further downstream analysis. Up to 198 input files of the type .pdf, .tsv, .csv, .txt or .xlsx can be processed at the same time.  

<figure class="image" >
  <p align="center"> 
    <img src="https://github.com/AndreHolzer/MetaPLMA/blob/master/images/MetaPLM-workflow.png?raw=true" width="580">
    <br>
    <em><b>Fig. 1:</b> Schematic diagram displaying the individual files and steps of the tool</em>
   </p> 
</figure>

The tool can be operated following graphical user interphases (GUI) on top of unerlying R markdown scripts. The tool has been tested on both Mac and Windows operating systems, predominatly analysing GC/MS data obtained from different algae samples. 



### Key Features

- **Simplicity**: The tool provides reproducible and scalable data analysis which can be executed across operating systems.
- **Integrated data extraction from .pdf and .xlsx files of common peak quantification tools**: Starting from .pdf files the tool allows easy extraction of GC/MS summary data from common pre-processing tools such as Thermo Xcalibur-TraceFinder or Shimadzu GCMS solution.



### **Documentation:**

Find the **full documentation** here: 
[https://andreholzer.github.io/MetaPLMA/](https://andreholzer.github.io/MetaPLMA/)



### **Quick links:**

- Jump to [Prerequisites](https://andreholzer.github.io/MetaPLMA/GS.html)
- Jump to [Installing](https://andreholzer.github.io/MetaPLMA/GS_T.html)
- Jump to [Usage](https://andreholzer.github.io/MetaPLMA/US.html)
- Jump to [Example/Test analysis](https://andreholzer.github.io/MetaPLMA/GS_E.html)
- Jump to [Support](https://andreholzer.github.io/MetaPLMA/AP.html)



## Citation

**If you use this pipeline for your analysis, please don't forget to cite:**

**DOI: …** (*<u>coming soon, please get in contact before using the tool</u>*)



#### **Developers**

- **Andre Holzer** - *Postdoctoal Reseach Associate, Department of Plant Sciences, Univeristy of Cambridge* [ORCID ID 0000-0003-2439-6364](https://orcid.org/0000-0003-2439-6364)

- **Matthew P Davey** - *Senior Research Associate, Department of Plant Sciences, Univeristy of Cambridge* [ORCID ID 0000-0002-5220-4174](https://orcid.org/0000-0002-5220-4174)

We would like to thank Monika Krolikowski for trailing the software. We'd also like to acknowledge Aom Buayam who contributed prototype some parts of this tool.



#### License

RESEARCH PURPOSES ONLY!

For more details view [full license agreement](https://github.com/AndreHolzer/MetaPLMA/blob/master/LICENSE)

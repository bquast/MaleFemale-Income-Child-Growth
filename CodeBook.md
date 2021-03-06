# CodeBook
Bastiaan Quast  
30 Jun 2015  

This file gives an overview of the files used for replicating the results of this project. For a general overview of the project please refer to the [README.md](/README.md) file.

Included Files
--------------------------------------------------------
* [import.R](/R/import.R): instructions on importing the Stata data files (.dta) into R and saving each wave to a separate .RData file
* [transform.R](/R/transform.W1.R): contains the R instructions to perform the required transformations to the data



Excluded Files
--------------------------------------------------------
These data source files are not included as they are licenced to be distributed only via the DataFirst portal. However, they can be created by using the R scripts described above and provided on the main page of the repository.


* [imported.RData](/imported.RData): contains all the imported separate data frames
* [transformed.Child.W1.RData](/transformed.Child.W1.RData): Contains the Child data frame with inserted need variables for Wave 1


Data
--------------------------------------------------------
The data used in this project has been collected and processed by the [National Income Dynamics Survey of South Africa][1]. Which is conducted by the Southern Africa Labour and Development Research Unit ([SALDRU][2]), which is based at the University of Cape Town’s School of Economics.

The data can be downloaded from the [DataFirst postal][2]. They can be downloaded here free of cost, once an account has been created.

At the time of writing, there are three available data sets (waves).

* [Wave 1][3]
* [Wave 2][4]
* [Wave 3][5]

The data is offered in three (or four) formats.

* SPSS
* Stata 12
* SAS
* (sometimes) Stata 8

For the purpose of importing into R, the Stata 12 format is prefered. Both the SPSS and the SAS format do not import very well and the Stata 8 format is obsolete. The Stata files are available here (when logged in).

* [Wave 1][6]
* [Wave 2][7]
* [Wave 3][8]

After having downloaded the above mentioned zip files, place them in the project directory (i.e. the same folder as this file is in, Gender-Child-Growth).

Replicate
--------------------------------------------------------
The procedure for replication is described step-by-step below, whereby each section corresponds to an R-file. In stead of running every file separately, all files can be ran in the correct sequence, by running the [replicate.R](/replicate.R) file. As described above, the source **zip files** need to be placed in the working directory.

Extract
--------------------------------------------------------
The [extract.R](/extract.R) file contains instructions for unzipping the zip files containing the **Stata 12** files. The script presumes the files are located in the working directory. All files will be unzipped to a new subdirectory called **stata12**.

We can list the extracted files.


```r
list.files('stata12')
```

```
## character(0)
```


Import
--------------------------------------------------------
The unzipped files are best imported with the R package called **foreign**. Full instructions for importing the data into R can be found in the [import.R](/import.R) file.

The imported data objects are saved to the file [imported.RData](/imported.RData).

Transform
--------------------------------------------------------
The transformations applied to data are described in the file [transform.R](/transform.R).

the transformed single panel data frame (pdata.frame, from the plm package) is saved to the [transformed.RData](/transformed.RData) file.

[1]: http://www.nids.uct.ac.za/
[2]: http://www.saldru.uct.ac.za/
[3]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/central/about
[4]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/451
[5]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/452
[6]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/453
[7]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/451/download/6038
[8]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/452/download/6001
[9]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/453/download/6052

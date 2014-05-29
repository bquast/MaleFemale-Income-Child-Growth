Replication
========================================================
Bastiaan Quast, bquast@gmail.com
--------------------------------------------------------

This file gives an overview of the files used for replicating the results of this project. For a general overview of the project please refer to the [README.md](/README.md) file.

Files
--------------------------------------------------------
* [import.R](/import.R): instructions on importing the Stata data files (.dta) into R
* [imported.RData](/imported.RData): contains all the imported separate data frames
* [transform.R](/transform.R): contains the R instructions to perform the required transformations to the data
* [transformed.RData](/transformed.RData): contains the transformed singel panel data frame (pdata.frame, from the plm package)


The data source files are not included as they are licenced to be distributed only via the DataFirst portal

Data
--------------------------------------------------------
The data used in this project has been collected and processed by the [National Income Dynamics Survey of South Africa][1]. Which is conducted by the Southern Africa Labour and Development Research Unit ([SALDRU][2]), which is based at the University of Cape Towns School of Economics.

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

After having downloaded the above mentioned zip files, place them in the project directory (i.e. the same folder as this file is in, Gender-Child-Growth). All three zip files contain a folder called **stata12** these should be placed directly in **this** folder, do **not** create a new folder with the same name as the zip file. Note, since the folders have the same names, a warning about merging will appear, since the containing files are named differently this will not be a problem, thus accept to merge the folders.

We now have a folder **stata12** directly in our working directory (i.e. the folder called Gender-Child-Growth) which contains all the source files.

We can check the contents of this folder using the R command:

    list.files('stata12')

It should look like this:

    [1] "Admin_W1_Anon_V5.2.dta"          
    [2] "Admin_W2_Anon_V2.2.dta"          
    [3] "Admin_W3_Anon_V1.2.dta"          
    [4] "Adult_W1_Anon_V5.2.dta"          
    [5] "Adult_W2_Anon_V2.2.dta"          
    [6] "Adult_W3_Anon_V1.2.dta"          
    [7] "Child_W1_Anon_V5.2.dta"          
    [8] "Child_W2_Anon_V2.2.dta"          
    [9] "Child_W3_Anon_V1.2.dta"          
    [10] "hhderived_W1_Anon_V5.2.dta"      
    [11] "hhderived_W2_Anon_V2.2.dta"      
    [12] "hhderived_W3_Anon_V1.2.dta"      
    [13] "HHQuestionnaire_W1_Anon_V5.2.dta"
    [14] "HHQuestionnaire_W2_Anon_V2.2.dta"
    [15] "HHQuestionnaire_W3_Anon_V1.2.dta"
    [16] "HouseholdRoster_W1_Anon_V5.2.dta"
    [17] "HouseholdRoster_W2_Anon_V2.2.dta"
    [18] "HouseholdRoster_W3_Anon_V1.2.dta"
    [19] "indderived_W1_Anon_V5.2.dta"     
    [20] "indderived_W2_Anon_V2.2.dta"     
    [21] "indderived_W3_Anon_V1.2.dta"     
    [22] "Link_File_W2_Anon_V2.2.dta"      
    [23] "Link_File_W3_Anon_V1.2.dta"      
    [24] "Proxy_W1_Anon_V5.2.dta"          
    [25] "Proxy_W2_Anon_V2.2.dta"          
    [26] "Proxy_W3_Anon_V1.2.dta"


Import
--------------------------------------------------------
The unzipped files are best imported with the R package called **foreign**. Full instructions for importing the data into R can be found in the [import.R](/import.R) file.

The imported data objects are saved to the file [imported.RData](/imported.RData).

Transform
--------------------------------------------------------
The transformations applied to data are described in the file [transform.R](/transform.R).

the transformed single panel data frame (pdata.frame, from the plm package) is saved to the [transformed.RData](/transformed.RData) file.


Estimate
--------------------------------------------------------




[1]: http://www.nids.uct.ac.za/
[2]: http://www.saldru.uct.ac.za/
[3]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/central/about
[4]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/451
[5]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/452
[6]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/453
[7]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/451/download/6038
[8]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/452/download/6001
[9]: http://www.datafirst.uct.ac.za/dataportal/index.php/catalog/453/download/6052
Overview
=====

Briefly, the program randomly subsamples the input dataset and estimates genetics 
parameters of each subsample such as mean number of alleles, allele frequencies, 
heterozygosities observed and expected under Hardy-Weinberg Equilibrium and inbreeding. 
It also estimates genetic distances between subsample and the original dataset. 
The output plots show comparisons of results from multiple sample subset sizes. 
The parameters are estimated for each locus, so no linkage disequilibrium assumptions are necessary.

Input file's format
=====

SaSii uses the datafile format from Structure (Fig 1 and 2) and 
accepts some minor variations of the original format, as described below. 
Both microsatellite and SNP data may be analysed with this package.  
All data must be included in a matrix in a single file, saved as csv. 

.. image:: /images/data_format1.png
    :alt: This example has one extra column (first column) with individual labels, 
    and one extra row (first row) with loci labels. Each individual is coded in a 
    single row and the two alleles of each locus are coded in two consecutive columns. 
    Microsatellite alleles are coded as fragment sizes, and missing data as zeros (“0”).

.. image:: /images/data_format2.png
    :alt: Example of alternative input datafile with 6 individuals and 6 SNP loci from a diploid species. 
    This example has two extra columns with individual labels (first column) and 
    sampling locations labels (second column), and one extra row (first row) with loci labels. 
    Each individual is coded in two consecutive rows because the two alleles of each 
    locus are on two consecutive rows. SNP alleles are coded as integers (e.g. 1 = A, 2 = C, 3 = G, 4 = T) 
    and missing data as “-9”.

Data for individuals are in rows, and the loci are in columns. 
In the default format, each line contains data of one individual and 
alleles from the same genotype are stored in consecutive columns. 
An alternative format with each individual genotype stored in 2 consecutive rows, 
with each locus in one column is accepted, but the user must change the default 
settings in the function (see details in section ___).  

Loci names must be short and simple. We suggest to use locus1, locus2, locus3 as loci names. 
Olther names may be used as long as they are short and only contain letters, numbers, dash and underscore. 

Genotypes may be coded as fragment size, sequential or random numbers, and as letters.  
Extra header columns may be present in the file. The user informs in which column the genotypic data starts. 
Default setting is one header column of individual names (Fig 1) and Fig 2 illustrates an example of alternative format). 


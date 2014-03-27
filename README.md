trox
====

An R Package for analyzing trisomic sequences

The current version has been tested for Linux and Mac only
=============================================================
To Install the package:

1)LINUX:
In the current directory, open an R session and type:
>install.packages("TroX_L.1.0.tar.gz")

After installation type

>library("TroX")

More information can be found by typing:

?TroX


2)mac

Make sure that you have gcc-4.2 installed on your computer
In the current directory, open an R session and type:

>install.packages("TroX_M.1.0.tar.gz",repos=NULL,type="source")

and follow the steps mentioned above

===============================================================
Sample Files
Three files are included in this folder:
1-T21.smp1
2-T21.smp2
3-T21.fam

1- T21.smp1:
Contains genotype data, as well as required information for each SNP for 12 full trios
where the POC is trisomy21. The triploid genotype data is available.
2- T21.smp2:

The same dataset as before with the difference that in one of the families data from the
father is not included.

3- T21.fam

List of families and ethnicity for each family.

Input File Format
====================================================================
The current version only accepts files of the following format:

Sample files:

The header must be as follows:

mapPos: position of each SNP in cM
Pos: position in bp
RS: integer part of the rs number for each SNP
<Popi>: frequency of the alternative allele in population i (should be compatible with the list of populations in the *.fam file)
M(fami): Maternal gentype for the ith family
P(fami): Paternal genotyoe for the ith family
C(fami): Trisomic proband's genotype for the ith family

Each row corresponds to a SNP (on a given arm of the chromosome),
ordered according to their physical location, so that the first SNP is
the most centromeric SNP.

Family file
List of family id's along with the ethnicity (e.g. AFR,EUR,ASN etc)

=======================================================================

Running the program on the sample files:

Assuming that you have opened an R session in the currect directory
where this README file is located, type:

library("TroX")
x<-ReadSamples("T21.smp1","T21.fam")
#to generate the posterior decoding path (which shows the crossover patterns)
PlotPath(x,fam=9910085)
#to generate a full report
Trx(x)
-----------------------------------------------------------------------
~                                                                                  

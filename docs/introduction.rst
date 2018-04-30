Introduction
============

Purpose
-------
To identify differentially expressed genes given a gene expression file containing two cell samples. Simplify the work of gene biologists.


Overview
--------
The web application has a simple interface with a single button [Upload and GO]. Our scientists upload a plain text file containing gene expression levels from two samples, representing two experimental conditions. Accepting the file, the software will return a table of differentially expressed genes and a scatter plot of these genes whose X-axis is control and Y-axis is treatment. If an invalid gene expression is given, the web application return a page informing the user to provide the correct format.


User Characteristics
--------------------
**Clinent**
	Gene biologists who need a web site to simplify their works.

**Site Maintainer**
	The owner of the website. The one who has some knowledge of sever maintaining.


Conventions
-----------

Terminologies
~~~~~~~~~~~~~
**Control Sample**
	A cell sample prepared in its normal condition.

**Treament Sample**
	A cell sample treated by special chemicals, or in which some genes are altered.

**Differentially Expressed Genes**
	The genes which have significantly different expression levels between two samples.

**Up-regulation**
	A gene is said to be up-regulated if it has higher expression in treatment than in control.


Glossary
~~~~~~~~
**OMG**
	Oh My Genes

**logFC**
	Log fold change of gene expression. log_2 [T/C], where T is the gene expression level from a treatment sample, while C is the gene expression level from a control sample


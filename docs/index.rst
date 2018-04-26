Software Requirements Specification for OMG Version 0.1
=======================================================

Abyss

Jin Xiongrong, 201632120123, 874898731@qq.com

DuZipeng, 201632120119, 826023157@qq.com


26 April 2018  


This document describes the Little Hill Lab's initial requirements for an online application (Oh My Genes) which allows our scientists to upload gene expression files and quickly get differentially expressed genes.  


Clients
-------
Biologists in our lab (potentially worldwide).


Purpose
-------
To identify differentially expressed genes given a gene expression file containing two cell samples.


Product
-------
A web application preferably using the Flask framework (http://flask.pocoo.org/).


Domain knowledge
----------------
Control sample - a cell sample prepared in its normal condition.
Treatment sample - a cell sample treated by special chemicals, or in which some genes are altered.
Differentially expressed genes - the genes which have significantly different expression levels between two samples.
Up-regulation - a gene is said to be up-regulated if it has higher expression in treatment than in control.
logFC - log fold change of gene expression.  log_2 [T/C], where T is the gene expression level from a treatment sample, while C is the gene expression level from a control sample.


Functionality
-------------

Overview
~~~~~~~~
The web application has a simple interface with a single button [Upload and GO].  Our scientists upload a plain text file containing gene expression levels from two samples, representing two experimental conditions.  Accepting the file, the software will return a table of differentially expressed genes and a scatter plot of these genes whose X-axis is control and Y-axis is treatment.  If an invalid gene expression is given, the web application returns a page informing the user to provide the correct format.

Input
~~~~~
A valid submitted gene expression file has the following format.  It is a TAB-delimited, plain text file with three columns (see the attached file for a full example).  The file contains an optional head line, followed by each gene's expression in a control sample (e.g., ControlSample) and in a treatment sample (e.g., KnockOutSample).

+-----------+---------------+----------------+
| gene_id   | ControlSample | KnockOutSample |
+===========+===============+================+
| AT1G01010 | 1.198558083   | 2.036161827    |
+-----------+---------------+----------------+
| AT1G01020 | 13.75736234   | 13.370796      |
+-----------+---------------+----------------+
| AT1G01030 | 0.833779536   | 0.203616183    |
+-----------+---------------+----------------+
| AT1G01040 | 9.58846466    | 7.126566394    |
+-----------+---------------+----------------+
| AT1G01046 | 0             | 0              |
+-----------+---------------+----------------+
| AT1G01050 | 23.81482799   | 21.10821094    |
+-----------+---------------+----------------+
| AT1G01060 | 0.625334652   | 1.221697096    |
+-----------+---------------+----------------+
| AT1G01070 | 1.719670292   | 0.950208853    |
+-----------+---------------+----------------+
| AT1G01080 | 28.34850421   | 25.24840665    |
+-----------+---------------+----------------+
| AT1G01090 | 58.26034505   | 42.96301455    |
+-----------+---------------+----------------+
| AT1G01100 | 1066.508249   | 1308.030358    |
+-----------+---------------+----------------+
| AT1G01110 |2.709783491    | 1.425313279    |
+-----------+---------------+----------------+

Output
~~~~~~~
The web application displays a table and a scatter plot given a gene expression file.

The table contains a list of differentially expressed genes with the following format:

gene_id  control_sample  treat_sample  log_2[FC]
AT1G01010  1.198558083  2.036161827  0.76

The scatter plot displays differentially expressed genes.  The X-axis is Control, and Y-axis is Treatment.
Replace 'Control' and 'Treatment' with appropriated column names if provided in the uploaded file.  The up-regulated genes are shown in red dots, and down-regulated genes are shown in blue.


Response time
-------------
<5 seconds.


Complications
-------------
How to set a threshold for logFC?


Tentative timeline
------------------
User Requirements Document: 3 April 2018
Requirements Q&A and elicitation:  13 April 2018
Software Requirements Specification: 1 May 2018
Acceptance test: 1 June 2018
Deployment date: 15 June 2018


Attachment
-----------
1. PlantGeneExpression.xls  [https://cloud.zjnu.edu.cn/share/b0cab8f698a3e7dfbf5d9fd819]



Frequently Asked Questions
--------------------------

Q:What are we supposed to write?
A: Please check the slide titled 'SRS ZJNU Style' (in lecture_slides02.pdf).  While you don't have to follow this template strictly, you are expected to include essentials elements such as purpose, use cases, change cases, response time, milestone, etc.  Including a few screen sketches would be great.  A good example of SRS can be found at http://web.uvic.ca/~cshen/seng321/project.html

Q: What should I submit?
A: You create an account on the Read the Docs website (https://readthedocs.org/) and send me a link to your SRS when done by May 1st.  See http://deeptools.readthedocs.io for an example.  I won't accept Word or PDF documents.

Q: What are change cases?
A: Change cases are changes that, although not explicitly mentioned in the user requirements document, might happen in the future.  Check lecture_slides02.pdf for Changes Cases.

Q: What does 'threshold' mean in the user requirements document?
A: Cutoff. You include genes with a logFC larger than this cutoff.

Q: Any coding at this stage?
A: No.  But if you have time, you could start reading the documentation of Flask (http://flask.pocoo.org/docs/0.12/) and trying it.

Q: How to use Flask?
A: Flask depends on Python.  So download Python 3.6.X from https://www.python.org/downloads/ and install it on your computer.  Then follow the instructions under the sections 'Flask is Fun' and 'And Easy to Setup' at http://flask.pocoo.org/.   For more information, check http://flask.pocoo.org/docs/0.12/quickstart/

Q: What is the word limit for my SRS?
A: 2,500 words, not including words in plots, tables and references (if any).  Make sure you run a spell checker before submitting your SRS.

Q: When should I submit my final report?
A: To be determined.

Q: We haven't learned python before, do you think that will prevent us from understanding Flask?
A: Python is simpler to learn than Java or C.  So I think Flask's learning curve is not steep.  A good start is to run the example in the section 'Flask is Fun' at http://flask.pocoo.org/.

---
layout: default 
title: Importing DBF files 
---

### The Problem

PANDA does not support importing DBF data files.

DBF is the format produced by long-lived database application <a href="http://en.wikipedia.org/wiki/DBase">dBase</a>. It is a common file-format for data produced from legacy systems.

### The Solution

DBF files should be converted to CSV before being imported into PANDA.

If you are not a programmer, you can open a DBF file using <a href="http://www.libreoffice.org/">LibreOffice</a>. Once open simply choose **Save As** from the **File** menu and then select "Text CSV" as the file type. If prompted with advanced options (delimiter, etc.) you may leave them set to the defaults.

<strong>Note:</strong> Excel can not open DBF files.

If you <em>are</em> a programmer or are comfortable using the command line then the faster method is to use <a href="http://csvkit.readthedocs.org/en/latest/scripts/in2csv.html">in2csv</a> from the <a href="http://csvkit.readthedocs.org/en/latest/index.html">csvkit</a> command line toolkit. This will read a DBF file and write a CSV file:

`in2csv filename.dbf > filename.csv`


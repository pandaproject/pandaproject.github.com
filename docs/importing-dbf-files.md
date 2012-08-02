---
layout: default 
title: Importing DBF files 
---

### The Problem

PANDA does not support importing DBF data files.

DBF is the format produced by long-lived database application [dBase](http://en.wikipedia.org/wiki/DBase). It is a common file-format for data produced from legacy systems.

### The Solution

DBF files should be converted to CSV before being imported into PANDA.

If you are not a programmer, you can open a DBF file using [LibreOffice](http://www.libreoffice.org/). Once open simply choose **Save As** from the **File** menu and then select "Text CSV" as the file type. If prompted with advanced options (delimiter, etc.) you may leave them set to the defaults.

**Note:** Excel can not open DBF files.

If you *are* a programmer or are comfortable using the command line then the faster method is to use [in2csv](http://csvkit.readthedocs.org/en/latest/scripts/in2csv.html) from the [csvkit](http://csvkit.readthedocs.org/en/latest/index.html) command line toolkit. This will read a DBF file and write a CSV file:

`in2csv filename.dbf > filename.csv`

**Note:** Whenever converting a file to import it into PANDA you should also upload the original as [related file](/docs/storing-related-files.html).

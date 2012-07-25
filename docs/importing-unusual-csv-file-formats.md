---
layout: default 
title: Importing unusual CSV file formats 
---

### The Problem

PANDA may fail to import CSV files that use unusual delimiters or have other formatting idiosyncracies. 

Although CSV is a widely-used format for exchanging data there is no standard for how it should be formatted. Because of this PANDA has to make an educated guess about the structure of any CSV file that is uploaded. On occasion this guess may be wrong and either cause an error, or cause the imported data to be malformed (typically visible in the Preview window after uploading a new file).

### The Solution

CSV files that fail to import should be resaved using a more standard format.

Although there is not defined standard for CSV formatting, there are commonly accepted parameters that will maximize the compatibility of the files. Abiding by these best practices will ensure PANDA can read your file.

It is often possible to correct a badly formatted CSV file by simply opening it in your spreadsheet application and saving it as a new CSV file. Depending on your application you may be prompted with advanced formatting options (delimiter, etc). Usually it is best to leave these on the defaults. In [LibreOffice](http://www.libreoffice.org/) you would choose **Save As** from the **File** menu and then select "Text CSV" as the file type.

If you are a programmer or are comfortable using the command line then the faster method is to use [in2csv](http://csvkit.readthedocs.org/en/latest/scripts/in2csv.html) from the [csvkit](http://csvkit.readthedocs.org/en/latest/index.html) command line toolkit. This will read many different CSV formats, but always outputs in the most standard format. If in2csv fails to guess the format of your file you can specify details about how it is formatted using various flags.

For example, to convert a file with tab delimiters you can use the `-t` option.

`in2csv -t tabbed.csv > standard.csv`


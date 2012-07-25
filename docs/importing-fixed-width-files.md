---
layout: default 
title: Importing fixed-width files 
---

### The Problem

PANDA does not support importing fixed-width data files.

Fixed-width is a file format where data is arranged in columns, but instead of those columns being delimited by a certain character (as they are in CSV) every row is the exact same length. The application reading the file must know how long each column is. There is no way to infer this from the file.

### The Solution

Fixed-width files should be converted to CSV before being imported into PANDA.

If you are not a programmer, you can open a fixed-width file using Excel or [LibreOffice](http://www.libreoffice.org/)'s Spreadsheet application. When using LibreOffice you will need to ensure the file has a `.csv` extension. Though this is incorrect, it will not allow you to open the file otherwise. Once open, select "Fixed width" from in Text Import window. Then in the table at the bottom of the window click to put dividing lines between the columns of data. Click **OK** once you have finished.

![](/images/libre-import-fixed.png)

Once you have successfully imported the data into your spreadsheet choose **Save As** from the **File** menu and then select "Text CSV" as the file type. If prompted with advanced options (delimiter, etc.) you may leave them set to the defaults.

If you are a programmer or are comfortable using the command line then the faster method is to use [in2csv](http://csvkit.readthedocs.org/en/latest/scripts/in2csv.html) from the [csvkit](http://csvkit.readthedocs.org/en/latest/index.html) command line toolkit. This will require you to create a "schema" file documenting the start and end points of the columns.

This example converts the Census 2000 fixed-width geographic headers file from fixed-width to CSV:

`in2csv -e iso-8859-1 -f fixed -s census2000_geo_schema.csv usgeo_excerpt.upl > usgeo.csv`

**Note:** A library of fixed-width schemas for common files is maintained as the [ffs project](https://github.com/onyxfish/ffs).


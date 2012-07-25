---
layout: default 
title: Handling unsupported Excel features 
---

### The Problem

PANDA supports importing Excel files, however, certain features may cause data to fail to import.

As a proprietary data format Excel files have a long and complicated history. PANDA does not can support all the features that Excel does. Some unsupported features are handled automatically, for example:

* The date `12/30/2011` in Excel will become `2011-12-30` in PANDA.
* A number shown rounded in Excel, `12`, will be expanded in PANDA, `12.011113`.
* A value with prepended zeroes, `000097`, will be simplified to `97`. (If the column contains only numbers and the leading zeroes were applied with a format.)
* When importing formulas, such as `=B1+5` PANDA will store the computed value only, `10`.
* Pivot tables and other embedded objects will be discarded.

In addition to these limitations only the first worksheet of an Excel workbook will be imported.

### The Solution

Excel files that fail to import should be resaved as CSV files prior to import.

If an Excel file fails to import for any reason the only solution is to export it to a CSV. This can be done in Excel or in another spreadsheet application, such as [LibreOffice](http://www.libreoffice.org/). In the latter simply choose **Save As** from the **File** menu and then select "Text CSV" as the file type. If prompted with advanced options (delimiter, etc.) you may leave them set to the defaults.


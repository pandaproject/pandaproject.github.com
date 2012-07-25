---
layout: default 
title: Dealing with two-digit year columns
---

### The Problem

When enabling column search for a date column that contains two-digit years, PANDA may place those dates in the wrong century.

Some datasets include dates with years specified using two-digits. For example, a NASA dataset might date the moon landing to "07/20/69". In cases like these it is impossible for PANDA's date parsing algorithm to know if the data indicates 1969 or 2069. In this case, we might reasonably default to 1969, however, things get trickier the closer the year gets to the turn of the century. Does `12 indicate someone is an infant or centenarian?

<strong>Note:</strong> This problem does not apply to Excel files. Two-digit years in Excel date columns are purely cosmetic formatting. The underlying data contains the full, four-digit year.

### The Solution

When a dataset contains a two-digit year column&mdash;for which you want to enable column search&mdash;you should transform it to a four-digit year before uploading it to PANDA.

Unfortunantely there is no one way to do this. Before you begin you should make sure you actually know what the century the data *should* be in. In some cases this is obvious from the context, but if it isn't you should consider requesting corrected data from your source.

If you know the correct century, for small datasets you may be able to make the corrections by hand. For larger datasets you may be able to use your spreadsheet application's **Format Cells** feature to change two-year dates to four-year dates. However, be aware that the application will be "guessing" what century the dates belong in. You should manually verify that it does so correctly. In <a href="http://www.libreoffice.org/">LibreOffice</a> **Format Cells** can be found in the right-click menu. 

![](/images/libre-format-cells.png)

Alternatively, if you have a programmer available to help you the ideal solution to this problem may be to write a small amount of code to reformat the file. In this case you may be able to take advantage of other information in the file (for example, the sort order) to make better inferences about the correct century for the dates.


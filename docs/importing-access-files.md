---
layout: default 
title: Importing Access files 
---

### The Problem

PANDA does not support importing Microsoft Access files.

There are actually two file formats produced by Access. Older files have an `.mdb` extension and newer files have a `.access` extension. Both formats are proprietary and neither format is directly supported PANDA. To make matters more complicated, Access files are actually *databases* that can contain a multitude of tables and the relationships between them. PANDA does not support database relationships.

### The Solution

Individual Access tables should be exported to CSV before being imported into PANDA. Relationships between tables will be lost.

Unfortunantely, there are only two ways to export a table from an Access file: using Microsoft Access and using the command line. Worse, the latter version does not always work. If you have Access you can export single tables from your the file by [TKTK].

If you are a programmer or are comfortable using the command line then you can try using <a href="http://linux.die.net/man/1/mdb-export">mdb-export</a> from the <a href="http://mdbtools.sourceforge.net/">mdb-tools</a> command line toolkit. This will export a table named `tablename` from an Access database named `filename.mdb`:

`mdb-export filename.mdb tablename > tablename.csv`

<strong>Note:</strong> mdb-tools only supports Access files with the `.mdb` extension. There is no alternative to Microsoft Access for exporting data from files with the `.access` extension.


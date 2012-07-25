---
layout: default 
title: Determining the encoding of a CSV file
---

### The Problem

When uploading or importing a CSV file PANDA raises an error related to the encoding of the file.

![](/images/panda-encoding-error.png)

Encodings are a complex subject, which we won't try to explain here. (Joel Spolsky has written an [excellent primer](http://www.joelonsoftware.com/articles/Unicode.html) if you want the technical details.) The important thing to know is that PANDA can not infer from a CSV file what encoding it is in. If the file contains characters which are not supported by the default encoding (known as `utf-8`) this can cause PANDA to generate errors.

The default is right in the large majority of cases, but when it isn't right figuring out the correct encoding can be very tricky.

### The Solution

Always ask your source what the encoding of the file is. Input the correct encoding after you select the CSV file to upload.

![](/images/panda-upload-csv.png)

If you have no way of finding out the correct encoding of the file, then try the following encodings, in this order:

* `utf-8`
* `iso-8859-1` (also known as `latin-1`)<br />(This is the encoding of all census data and much other data produced by government entities.)
* `utf-16`

If none of these work the likelyhood you are going to determine the encoding without additional information from the source is very low. In theory you may be able to guess the encoding based on the [language of the author](http://en.wikipedia.org/wiki/8859#cite_ref-0), however this not a recommended practice.


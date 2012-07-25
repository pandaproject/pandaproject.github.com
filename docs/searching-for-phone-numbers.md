---
layout: default 
title: Searching for phone numbers
---

### The Problem

Phone numbers are not always formatted the same way, so a simple search may not turn up all possible matches.

Phone numbers come in a dizzying variety of formats, including:

* 5556667777
* 555-666-7777
* (555)666-7777
* (555) 666 7777
* +1 555-666-7777
* +15556667777

Because of the array of complexity involved, the PANDA search engine may not be able to identify all matches if you search for a simple, ten-digit number.

<strong>Note:</strong> Social Security Numbers, if delimited by whitespace, may also require this technique, but this is rare.

### The Solution

It is impossible to account for every possible way that a phone number may be formatted, however, by carefully structuring a query we can uncover the vast majority of them. PANDA processes all numbers that are put into it such that a simple search will match a phone numbers in the most common formats.

Query `5556667777` matches:

* 5556667777
* 555-666-7777
* (555)666-7777
* (555) 666 7777

However, it will not match variations that include whitespace or the international code (+1). In order to match any variation, *except* international codes, the following will suffice.

Query `5556667777 or "555 666 7777"` matches:

* 5556667777
* 555-666-7777
* (555)666-7777
* (555) 666 7777
* +1 555-666-7777

The second part of the query will match versions of the number that are delimited by whitespace (or other characters). The quotes ensure each part of the number is matched in order. However, this will still not match international codes. In order to match these we need to add two more parts to the query:

Query `5556667777 or "555 666 7777" or 15556667777 or "1 555 666 7777"` matches.

* 5556667777
* 555-666-7777
* (555)666-7777
* (555) 666 7777
* +1 555-666-7777
* +15556667777

This should match virtually any phone number format.


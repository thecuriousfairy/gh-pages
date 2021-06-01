---
layout: post
title:  "My Own Markdown Cheatsheet"
date:   2021-05-01 21:14:31 -0600
---
# Introduction

Jekyll uses kramdown as it's markdown flavor of choice.  I have used markdown off
and on for various projects at work, so it's not completely foreign to me.  However,
I am super forgetful and if I am going to use it for the foreseeable future I am
going to need some type of cheatsheet.  This page is going to be that for me.  I
know it will likely grow over time as I find new things I want to be able to do,
but for now this is what I need or think I will want in the short time ahead.

# Cheatsheet

### Headers

Notes: A header must be preceded by a blank line.

~~~
#       H1 Header
##      H2 Header
###     H3 Header
####    H4 Header
#####   H5 Header
######  H6 Header
~~~

### Code

Notes: Code block works with any number of ~ as long as the second set has more
than the first set.  Yes this means my original box has more than this so that
it would actually show what's going on.
~~~~~~
~~~
code goes here
~~~
~~~
but this also works
~~~~~
~~~~~~

### Paragraphs

Notes: I can hit "enter" in the middle of a line of text in my editor, and it will
not be a paragraph or line break.  An extra new line will create a paragraph.
Two spaces at the end of a line will create a line break.

~~~~
This is not
a new paragraph

But this would be a new paragraph

You can't see the spaces but  
this would create a line break
~~~~

This is not
a new paragraph.

But this would be a new paragraph

You can't see the spaces but  
this would create a line break

### Lists

#### Ordered Lists

~~~
1. Item 1
2. Item 2
   This will continue on the same line as Item 2
3. Item 3
4. Item 4
~~~
1. Item 1
2. Item 2
   This will continue on the same line as Item 2 (but it's on a new line)
3. Item 3
4. Item 4

#### Unordered Lists

~~~
* purple
* orange
* pink
~~~
* purple
* orange
* pink

### Tables

#### Simple Tables

~~~
| cell 1 | cell 2 | cell 3 |
| row 2 cell 1 | cell2 | cell 3 |
~~~

| cell4   | cell5   | cell6   |
| cell1   | cell2   | cell3   |

#### Table With Headers

~~~
| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
~~~

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
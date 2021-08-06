---
title: Psychopy Tips and Tricks
linktitle: Psychopy 
toc: true
type: docs
date: "2019-05-05T00:00:00+01:00"
draft: false
menu:
  example:
    parent: Computer Stuff
    weight: 1

# Prev/next pager order (if `docs_section_pager` enabled in `params.toml`)
weight: 1
---

## How to update to Psychopy3 on your computer

As of 11/1/2019, the standalone package to download Psychopy3 from the [Psychopy website](https://www.psychopy.org/download.html) does not contain the correct dependencies required for using some of the features we need in the LMCL (such as the pyo library for audio and voice keys).  

The work around is to download the source code via the terminal and adjust the dependencies yourself. Instructions for this are outlined on the Psychopy website but require additional manipulation to work in the capacity required for this lab. Additional instructions have been outlined below.

### For Mac users:
- OS must be updated to version 10.12 or higher
- must be running python 3.6 or higher
- use pip3 to install pyo
- use pip3 to install pyglet == 1.2.4 

After the above is complete can you can:
 
<b>pip3 install psychopy</b>

To now open and run psychopy3, open the command line terminal and simply type "psychopy"

### For PC users:

Follow the instructions on the [Psychopy website](https://www.psychopy.org/download.html).


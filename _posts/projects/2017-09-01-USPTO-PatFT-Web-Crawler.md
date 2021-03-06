---
layout: media
title: "Web Crawler of USPTO PatFT Database"
categories: projects
excerpt: "Crawler for batch information gathering from US patent database"
share: true
tags: [Python, Crawler, PatentAnalysis]
image:
  feature: 
  teaser: USPTO/prv.jpg
---

[github link](https://github.com/mattwang44/USPTO-PatFT-Web-Crawler){:target="_blank"}

Crawler for fetching information of US Patents and batch PDF download.  
preview:  
<img src="../../images/USPTO/preview.png">


## Motivation
I've participated in patent analyzation project since Apr. 2017. Our team need to search with certain query on PatFT and examine if each resulting patent is suitable for our topic and then analyze suitable patents. I found out that we can download bulk patent data only by searching certain words, names, or regions with [Download patent data](https://developer.uspto.gov/data/bulk-search) and [PAIR Bulk Data](https://pairbulkdata.uspto.gov) from [USPTO's Open Data Portal](https://developer.uspto.gov/), which aren't very useful for us, and suitable tools that can be found on the Internet are all charged. So, I started to write a Python scripts containing basic functions, which accelerated the progress of project. To made this program more user friendly, I revised the code and made an UI with PyQt5.
  
 
## Download Execution File 
The source code has packaged with pyinstaller in Windows  
1.[Normal package](https://drive.google.com/open?id=0B4zCzLRoIx8eeWRwN1M3dFNTUE0)  
2.[Single executable file](https://drive.google.com/open?id=0B4zCzLRoIx8eeG4wbUZDdVdrTDg)


## Instruction 
You can follow the instruction below or watch this [video](https://www.youtube.com/watch?v=zqSEqUk2kgg). It should be easy to learn :).  


### Patent Fetcher
(1) Insert PN (2) Filtering conditions (3) Information to be fetched (4) PDF type to be downloaded (5) Table  
<img src="../../images/USPTO/ins.png">

1. Insert the patent numbers (PNs) to be processed in following ways:  
 (a) Choose a **CSV file with PNs in the first coulumn** 
   ([example](https://github.com/mattwang44/USPTO-PatFT-Web-Crawler/blob/master/PN_sample.CSV)).  
   (b) **Search with query** (The query should examined on PatFT first)  .
   The PNs should be shown in the table.

2. (Optional) Filtering the shown PNs with **setting the patent types, range of application date & issue date**.  
   The filtered PNs are also shown on the table but will be deleted in the end of this process.

3. **Fetching the information** of patents shown in the table by web crawling.  

4. Download **PDF of full-text or drawing section** (or both simultaneously) of patents shown in the table.

5. The **table can be saved** as a CSV file anytime.  


### Browser  
<img src="../../images/USPTO/browser.png">
In the second page, you can insert PN to show the PatFT web of this patent or open PDF with your default browser.


## Caution
1. The program has some problems when fetching information of the patents issued before 1976. Still working on it.
2. Searching with long query takes a lot of time, same as it takes on PatFT ([example](http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=0&p=1&f=S&l=50&Query=%28%28%28CPC%2FA62B%24+OR+CPC%2FB65H%24%29+OR+CPC%2FF16D%24%29+OR+CPC%2FB66D%24%29+AND+%28%28brak%24+OR+lock%24%29+OR+%28retract%24+OR+rewind%24%29%29+AND+%28%28%28lifeline+OR+lanyard%29+OR+%22safety+line%22%29+OR+cable%29&d=PTXT)). I tried using threading in the program but it leads to more time consumed, and multiprocessing leads to bad connection. If you have a long query with less than 500 results, copying the patents number to a CSV file on your own and insert the file should be faster.  
3. If you encountered any problems or have any suggestion (like adding other function), feel free to [contact me](http://mattwang44.wixsite.com/main/contact)!



  
 

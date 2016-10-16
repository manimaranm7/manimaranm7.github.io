---
layout: single
title: The No-Linker concept in .NET
date: '2004-02-11 22:05'
author: peakbyte
comments: true
categories: [BackToBasics, VM.DotNET]
---
Yesterday night while returning to my home, dropped in to my friends startup company. It so happened that I had to talk about “Gettting started with C#”.
<br />
<br />I thought it would be great to write the HelloWorld program and start disecting it. It so happened that, we went on to discuss on topics like:
<br /><ul><li>Whats the difference b/w compiler and interpreter?
<br /></li><li>What happens from the time of double click of an windows application till some output is got? We had gone as far as to see what is an OS loader, how processor executes instructions, where are instructions stored and all those stuff which should have been discussed at the college days.
<br /></li><li>Defination of Object.
<br /></li><li>Seing the anology of an object and me.
<br /></li><li>Seing the anology of a class and human class.
<br /></li><li>Class methods and Instance methods.
<br /></li><li>Whats the difference b/w an *.exe and *.dll file
<br /></li><li>About PE file format.
<br /></li></ul><p>The most important point of the talk was when I understood that .NET does not have the concept of a <strong>Linker</strong> .
<br /></p><p>There is no linker because there is no such thing like statements in C/C++.
<br /></p><p>I could not resist to go deep further into the Metadata Tables and related basic stuff. Realized as to why Jeff Richter has given priority to Metadata and Assemblies in his excellent book “Advanced .NET programming”.
<br /></p><p>I am out to see whats the scenario in Java Technology case. (Recently lots of comparison is happening b/w Java Technologies and .NET) The best link of all is <a href="http://www.dwheeler.com/java-imp.html">http://www.dwheeler.com/java-imp.html</a> </p>

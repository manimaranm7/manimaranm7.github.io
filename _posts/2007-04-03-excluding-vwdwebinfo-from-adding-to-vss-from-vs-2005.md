---
layout: single
title: Excluding vwd.webinfo from adding to VSS from VS 2005
date: 2007-04-03 10:58
author: peakbyte
comments: true
categories: [Problem, SourceControl.VSS, Tools.IDE]
---
When I have a ASP.NET WebSite (NOT WebApplication), I notice the presense of vwd.webinfo in my VS 2005 solution. The problem is the annoyance when it shows as a new source control item. (with a plus sign next to the filename). So, when ever I do a "Pending Checkins"/"Checkin", it is included as part of the pending items.

<a href="http://63.134.238.61/blogimages/Excludi.webinfofromaddingtoVSSfromVS2005_A1C1/webinfo_in_sln10.jpg"><img src="http://63.134.238.61/blogimages/Excludi.webinfofromaddingtoVSSfromVS2005_A1C1/webinfo_in_sln_thumb8.jpg" alt="" /></a>

At the moment I am taking care to uncheck this file and then do the checkin.

<a href="http://63.134.238.61/blogimages/Excludi.webinfofromaddingtoVSSfromVS2005_A1C1/pending_checkin3.jpg"><img src="http://63.134.238.61/blogimages/Excludi.webinfofromaddingtoVSSfromVS2005_A1C1/pending_checkin_thumb1.jpg" alt="" width="485" height="59" /></a>

But, it would be nice to have tell VSS to exclude this file (or set of files) from trying to add to VSS.

I've also thought about "exclude from this project" option in Solution Explorer within VS 2005, but then it adds a file called vwd.webinfo.exclude and then this shows up in pending checkins once again.

Using the VSS client, there is a facility to include FileTypes. To my surprise, the *.webinfo was not included but still the VS 2005's VSS plug-in tries to add it.

I've never managed to get an solution to this problem yet. Hopefully something might turn out at a later time.

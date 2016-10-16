---
layout: single
title: Web client software factory - Hands-on-lab
date: '2008-09-26 11:35'
author: peakbyte
comments: true
categories: [Arch.Web, FX.Web.ASPNET, Solution]
---
<p>Having decided on giving the WCSF a try, I had a pretty smooth experience with installing WCSF. </p> <p>The February-2008 release of WCSF does not use the Enterprise Library 4.0. It uses Enterprise Library 3.1. Although, the EntLib 3.1 is sufficient for WCSF-Feb'08, it just feels good to have and build upon the latest version. It took a few <a href="http://www.codeplex.com/websf/Wiki/View.aspx?title=HowTo WCSF EntLib4&amp;referringTitle=Others" target="_blank">careful steps</a> to get the WCSF working with EntLib 4.0. And even after that, at times, the guidance packages generate code that still uses EntLib3.1. This is not a major problem because I was able to re-reference the projects to the latest EntLib 4.0 assemblies.</p> <p>The foremost concept to understand is the Modular structuring of the Web Application. </p> <p>Then comes the understanding of Model-View-Presenter pattern. It took a while for me to figure out the role of Controller. </p> <p>There is also the concept of a Service that gets consumed by a Controller. This Service has nothing to do with Web Services.</p> <p>In fact, there is much more fundamentals to understand than I could discover in the hands-on-lab sessions.</p> <p>The best resource (and by far the best writing) to explain concepts related to WCSF is <a href="http://shrinkster.com/12ig" target="_blank">Simon Ince's blog series</a>. His posts made me understand the purpose of WCSF and have also inspired me on the various architectural considerations.&nbsp; </p>

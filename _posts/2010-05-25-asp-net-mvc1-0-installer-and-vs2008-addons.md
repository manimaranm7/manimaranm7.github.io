---
layout: single
title: ASP.NET MVC1.0 installer and VS2008 AddOns
date: '2010-05-25 13:15'
author: peakbyte
comments: true
categories: [Uncategorized]
---
<p>Today I tried all things in vain to try and install ASP.NET MVC 1.0 on to my machine and it just kept failing. </p>  <p>Possible causes, upon Binging focused on conflicting Visual Studio 2008 addons. Among the list of such addons, I had PowerCommands. But, despite uninstalling it, mvc installer complained.</p>  <p>Then I begun uninstalling other possible addons (not listed in the mvc installer readme file). The first to go was SlickEdit gadgets.</p>  <p>Lo and behold, the MVC installation was successful.</p>

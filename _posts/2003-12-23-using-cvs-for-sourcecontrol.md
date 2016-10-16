---
layout: single
title: Using CVS for SourceControl
date: 2003-12-23 17:53
author: peakbyte
comments: true
categories: [Problem, Solution, SourceControl, SourceControl.CVS]
---
<span style="font-family:trebuchet ms;font-size:85%;">"An alternative to VSS" was the requirement. Decided to plunge into CVS. SA had the CVS server installed on a Linux machine. My task was to find and explore the various CVS clients for Windows.
<br /></span>
<br /><span style="font-family:trebuchet ms;font-size:85%;">First, tried </span><a href="http://www.cvshome.org/"><span style="font-family:trebuchet ms;font-size:85%;">WinCVS</span></a><span style="font-family:trebuchet ms;font-size:85%;">. Then went on to look for CVS plugins for VS.NET. Found </span><a href="http://dotnetjunkies.com/WebLog/mani.net/admin/www.jalindi.com/igloo/"><span style="font-family:trebuchet ms;font-size:85%;">Jalindi Igloo</span></a><span style="font-family:trebuchet ms;font-size:85%;">. Igloo was a major failure inspite of a detailed article on the CodeProject.
<br /></span>
<br /><span style="font-family:trebuchet ms;font-size:85%;">Then looked into the </span><a href="http://www.tortoisecvs.org/"><span style="font-family:trebuchet ms;font-size:85%;">TortoiseCVS</span></a><span style="font-family:trebuchet ms;font-size:85%;">. Inspiring integration with the windows shell. The ease of use was spell bounding. The help accompanying installation gave a detailed look into the two different methodologies for SourceControl namely, Lock-Modify-Unlock and Copy-Modify-Merge. TortoiseCVS uses C-M-M model.
<br /></span>
<br /><span style="font-family:trebuchet ms;font-size:85%;">A VS.NET plugin for TortoiseCVS was under development. I tried it but failed to Check out a module.</span>
<br /><span style="font-family:trebuchet ms;">
<br /><span style="font-size:85%;">Then looked into the </span></span><a href="http://subversion.tigris.org/"><span style="font-family:trebuchet ms;font-size:85%;">SubVersion</span></a><span style="font-family:trebuchet ms;font-size:85%;"> alternative for CVS. Even this follows C-M-M model. But, the VS.NET plugin developed for SubVersion, </span><a href="http://ankhsvn.tigris.org/"><span style="font-family:trebuchet ms;font-size:85%;">ankhsvn</span></a><span style="font-family:trebuchet ms;font-size:85%;"> looks good by seing the Screen Shots. Got to install svn soon and try it. The free book on subversion is excellent.</span>
<br /></span><span style="font-family:trebuchet ms;">
<br /><span style="font-size:85%;">Then went on to read the Microsoft's “Team Development Guide” from </span></span><a href="http://www.microsoft.com/patterns"><span style="font-family:trebuchet ms;font-size:85%;">Patterns&amp;Practices</span></a><span style="font-family:trebuchet ms;font-size:85%;">. This guide is indispensible for VSS and VS.NET users.
<br /></span>
<br /></span><span style="font-family:trebuchet ms;font-size:85%;">Another Microsoft Article from MSDN was very </span><a href="http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dv_vstechart/html/vetchWebProjectsSourceControlIntegrationInVisualStudioNET.asp"><span style="font-family:trebuchet ms;font-size:85%;">good</span></a><span style="font-family:trebuchet ms;font-size:85%;">. This is related to SourceControl and build control for Web Projects.
<br /></span>
<br /><span style="font-family:trebuchet ms;font-size:85%;">For now, using WinCVS and TortoiseCVS together.
<br /></span>
<br /><span style="font-family:trebuchet ms;font-size:85%;">Waiting for something to happen.........</span>
<br />

---
layout: single
title: From VSS to CVS; From CVS to SVN
date: '2005-02-01 10:21'
author: peakbyte
comments: true
categories: [Design, Problem, Solution, SourceControl.CVS, SourceControl.SVN, SourceControl.VSS]
---
Hmm.....After <a href="http://msdn.microsoft.com/vstudio/previous/ssafe/">VSS</a> came <a href="https://www.cvshome.org/">CVS </a>and now after CVS it's time to try out <a href="http://subversion.tigris.org/">SVN</a>!

Yesterday, I was finally determined to make my machine a build system(with WinXP SP2 Pro) for which I had to install and configure <a href="http://confluence.public.thoughtworks.org/display/CCNET">CruiseControl.NET</a>. For which I had to install VSS. Then I thought of CVS (because, I was comfortable with CVS way of doing things for the past 1 year). Oh...then I thought of SVN (because, SVN is to be a compelling replacement for CVS).

The best part of SVN is the availability of the free e-book which is quite exhaustive. I was indeed more happy to read the <a href="http://tortoisesvn.tigris.org/">TortoiseSVN</a> e-book because it gave detailed steps to install the SVN Server and not just the TortoiseSVN Client.

Since I did not have Apache Web Server in my system, I prefered the SVNServe type of SVN Server which listens on port 3690. With that I had my svn server setup but before running the server, I read a piece of information in the book which said that the svnserve.exe can be run as a windows service using a wrapper called <a href="http://dark.clansoft.dk/~mbn/svnservice/">SVNService</a>. Without much thought, I tried running the svnserve as windows service.

But, to my despair when I tried to view the repository which I had just created using TortoiseSVN, I could not find the repository using the repo-browser of TortoiseSVN. Something has gone wrong somewhere....After 30 minutes, I started to suspect the SVNService wrapper. So, instead of going to that level of abstraction, I decided to run the svnserve manually using command prompt. And lo there was Windows XP SP2 in action asking my permission to unblock the port 3690. Phew! that was a relief. After unblocking it, I reverted back to SVNService.

There ended my initial adventure with SVN which was quite less exciting than my earlier ones with CVS and TortoiseCVS. I am expecting the real thrill when I start using ASP.NET application with SVN.

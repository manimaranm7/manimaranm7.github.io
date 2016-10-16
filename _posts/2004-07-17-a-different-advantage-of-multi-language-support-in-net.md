---
layout: single
title: A different advantage of multi-language support in .NET
date: 2004-07-17 21:47
author: peakbyte
comments: true
categories: [KM.Team, Lang.C#, Lang.VBDotNet, Solution, VM.DotNET]
---
Today, I had to create the skeleton VS.NET solution along with the different .NET projects that would go into the solution for a new project at my workplace.
<br />
<br />The reason I chose today as the day for this is that I could see someone starting to go ahead with the project development like some student hacking his way around. I have lost the patience to even look at such kind of coding. Worst is the case when there are files named “WebForm1.aspx” and “WebApplication1.sln”. If not today then never it will be. If substantial amount of coding goes into the project then the natural tendency to resist change occurs and the result is spaghetti code. ( ”Denial is the most predictable of all human responses” - from Matrix - <a href="http://www.neoandtrinity.net/">http://www.neoandtrinity.net/</a>)
<br />
<br />In my previous ASP.NET web application project, majority of the time was spent on setting up the environment and learning new stuff.( VSS to CVS transition, 3-Tier Architecture, User Interface Process, Authoring Web Pages, Web Menu, User Controls, Authentication &amp; Authorization, Coding Guidelines, Javascript and Asp.Net co-existence, DataGrids, Session Expiration, Understanding Struts to understand MVC, Deployment etc...). In fact, every damn thing was new. Not much time was devoted on implementing most of the suggestions in “Real-world tips for Real-world web application” web-cast by Paul D. Sheriff, President, <a href="http://www.pdsa.com/">PDSA</a> Inc. Almost all the tips are right on target and gives the viewer enormous confidence and courage to immediatly try including them in their current project. And quite a few of the tips were incorporated. I was scared to experiment more due to the UIP application block being used (which in itself is mind-bogling stuff).
<br />
<br />This project will not use the UIPAB and hence the decision to start with business logic coding only when all the real-world tips are included. At this precise moment, I've included 6 of 10 tips in this project (The coding for which started about 9 hours back). A more <a href="http://www.microsoft.com/asia/solutionmarketplace/download_detail.asp?id=42&amp;sLanguage=1">elaborate </a>webcast on N-Tier programming (”Designing LOB applications using Asp.NET”) was refered and hence a different project folder structure has been adopted.
<br /><ul><li>N-Tier programming (done)
<br /></li><li>Application Settings (done)
<br /></li><li>User Interface
<br /></li><li>Base Page Class (done)
<br /></li><li>Track Users (next in the task queue)
<br /></li><li>Exception Management (done)
<br /></li><li>Session Variable Usage (done)
<br /></li><li>Manage Unhandled Exceptions (done)
<br /></li><li>Security (doing...)
<br /></li><li>Performance
<br /></li></ul><p>Now, let me come to the relation of this post with that of its subject. The code sample provided and refered by Paul D. Sheriff was written using VB.NET and the project I am developing is using C#. So, most of the time I had to replicate the code in C# for which I had to understand VB.NET code also. This process of looking at a code written in another .NET language and writting the same functionality in another .NET language is very fascinating. Some of the syntax I used to take for granted were made to understand.</p><p>
<br />Now, one might argue that this can be done with other languages also. Advantage in this case is that both VB.NET and C# uses the underlying FCL and thus makes it very easy to do the conversion and hence the learning. Imaging doing the same from Java to C# (I guess this might also be easy owing to the fact that many OSS existing in Java are now being written in C#).
<br />I've now decided that to understand any code, best method is to re-write the code using some other language. I think VB.NET developers will get a better grip on Object-Oriented languages by using this technique. </p><p>
<br />Also, for the first time I have thought about the number of lines of coding that has gone in today. Stumbled upon the “<a href="http://www.anticipatingminds.com/Content/Products/devMetrics/devMetrics.aspx">devMetrics</a>” tool for C# code analysis and reporting. Unfortunately, It is not enabling the Analyze... option from the VS.NET 2003 IDE. But, I could generate the report using the Command Line facility and found that the amout of code written today by me is approx. 250 lines. </p><p>
<br />Ok... Time to take a nap and go home in the morning.... </p>

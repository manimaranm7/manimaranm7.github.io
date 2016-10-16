---
layout: single
title: My first experiments with NUnit and NAnt!
date: '2004-10-27 21:11'
author: peakbyte
comments: true
categories: [Solution, Tools.Build, Tools.Testing]
---
Finally I got a chance to use these tools (<a href="http://nant.sourceforge.net/">NAnt</a> and <a href="http://www.nunit.org/">NUnit</a>)

The first to be used was NUnit 2.2 and had problems using it because I don't have permissions to install any assemblies into the .NET 1.1 Global Assembly Cache. So, I had to obtain the source and did the manual installation of copying all the required assemblies into a single folder. Then I set up the Path Environment variable to include path where these assemblies were put.

After doing this I went cruising my way creating cool unit tests for my own library under construction. It all worked fine and I used the NUnit-GUI to test my applications.

Then came the second half of the fun! I had to now use the NAnt build tool. So, went ahead and downloaded the binaries for NAnt. As done earlier, set up the environment variable path. I was lazy and tried to use the build of my VS.NET projects using the task. Boom! A enormous list of errors and exception finally thrown at me by the NAnt utility. Now, I did not want to use the <a href="http://nant.sourceforge.net/help/tasks/">task</a> and went ahead to create my own directory structure (deciding where each output should go into and also keeping in mind the NUnit tests to be run automatically by NAnt) and corresponding task in my build.xml file.

The most frustrating or shameful mistake I did was to forget the fact that xml tagging is case sensitive. So, all I was getting was errors reporting FileNotFound. Spent nearly 2 hours in wain untill I was forced to get reminded of this fact that xml tagging is case sensitive!

And that is not the end of it! When tried to use the task got the exception that NAnt could not find the nunit.framework.dll assembly (as expected, because i have not installed the NUnit assemblies into the GAC and that is because I DON'T HAVE PERMISSIONS). Then I went on with the task to execute the “nunit-console.exe”. Now the whole fun started :) Again the problem of nunit.core and nunit.framework assemblies not found problem.

The problem was that I did not bother about nunit.core and nunit.framework assemblies when using the nunit-gui because they were in the same folder as that of nunit-gui.exe. But, now when I run nunit-console, the present working directory will be the location where the build file is present and thus nunit-console cannot find the nunit.core and nunit.framework assemblies.

So, the only solution left for me was to copy the nunit.core and nunit.framework assemblies from the installed folder (the path is hard coded in the build file; I do not like to do that) to the present working directory. That solved the main problem. But I really failed in transforming the TestResult.xml produced automatically by NUnit-console to a proper html output using the “Summary.xslt”. Too much to handle for a single day may be.. So I am giving up on that and am contended with the error output files.

The immediate task facing me now is to use the al.exe for linking the modules just compiled using NAnt's build process into a single assembly and placing in the GAC. But hold on, I do not have permissions to install an assembly into the GAC! Instead, I have the <a href="http://sharedsourcecli.sscli.net/">SSCLI's </a>GAC. hmmm, that would take more time I guess.

I just wish some kind of USER Specific GAC is provided in .NET! (or may be permissions can be granted to install the assemblies generated and strongly named by the CURRENT USER into the GAC). Got to look into .<a href="http://www.microsoft.com/technet/itsolutions/net/maintain/opnetapp.mspx">NET Operation </a>documentation for all these stuff!

Ok. Now time to shift to <a href="http://sharedsourcecli.sscli.net/">Rotor</a> and leave .NET for a while! Phew!

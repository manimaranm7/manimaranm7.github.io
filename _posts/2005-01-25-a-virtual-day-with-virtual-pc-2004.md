---
layout: single
title: A Virtual Day with Virtual PC 2004
date: 2005-01-25 23:34
author: peakbyte
comments: true
categories: [OS.Tools, Solution]
---
Today was a day dedicated to <a href="http://www.microsoft.com/windows/virtualpc/default.mspx">Virtual PC 2004</a>.

My colleague (infact classmate) Ankur was the first one to have installed Virtual PC 2004 and have it up and running. His setup was quite surprising. He was able to install Virtual PC 2004 on a Windows XP Home edition. His one and only GUEST machine was Windows Server 2003. Infact, Virtual PC 2004 does not officially support this setup. Ankur's need was quite different than mine. Since he had a laptop and a desktop computer he could afford for that kind of setup wherein he would be using the Windows Server 2003 for SQL Server 2000 and Source Control.

Since I don't have the comfort of having a separate physical server, I wanted to install Windows Server 2003 as my GUEST machine with the HOST being a Windows XP Professional. The idea was to create a Virtual Network with the HOST and GUEST being the only nodes in the network. The excellent help provided by Virtual PC 2004 was useful only to get started.

I had to first install the new network adapter(Microsoft Loopback Adapter) using Add Hardware Wizard on my HOST machine and provide the HOST with a static IP address (192.168.1.1) for the connection associated with LoopBack Adapter. The similar proceedure was followed in my GUEST machine with the IP address being 192.168.1.2. I also changed the number of network adapters for the GUEST machine in the Virtual PC Console to include the Microsoft Loopback Adapter.

I restarted my GUEST machine and expected my HOST to detect the GUEST.

That looked like a distant future for me. Basically I could not get it to work.
On googling, I found a link to a Virtual PC guy's blog which explains a subtle <a href="http://blogs.msdn.com/megand/articles/271852.aspx">problem</a>. A chicken and egg kind of problem is what he says. Oh...and here is the actual <a href="http://blogs.msdn.com/Virtual_PC_Guy">Virtual PC guy's blog</a>. Now then I had to realize it will take quite more strain to make this thing work or conclude that it will NOT work. At this point I give up for the day and go to reality by taking a nap and iterating on this stuff tomorrow........

LINKS:
<ol>
	<li><a href="http://vpc.visualwin.com/">A-Z on Virtual PC</a></li>
	<li><a href="http://www.microsoft.com/windowsserversystem/virtualserver/default.mspx">Virtual Server</a></li>
	<li><a href="https://msevents-eu.microsoft.com/cui/EventDetail.aspx?culture=en-GB&amp;eventid=118752631">TechNet Virtual Server Technical Briefing in Edinburgh</a></li>
</ol>

---
layout: single
title: TIP - Copy/Paste Columns to Multiple Tables in SQL Server
date: '2009-09-19 15:29'
author: peakbyte
comments: true
categories: [DB.SQLServer, Problem, Solution, Tools.SQL]
---
Here is a tip I discovered today while at work. I had earlier postponed the addition of common columns needed for all the tables (columns needed for auditing purposes like AddedDate, AddedBy etc.). But, the time had come now to type in and set the properties for columns on all tables one by one. I finished adding these columns to the first table. When on the second table, my laziness kicked in and wanted an easier way to do this mundane task. So,
<ol>
	<li>Opened the design of table1 using SQL Server Management Studio.</li>
	<li>Selected the last 4 columns.</li>
	<li>Ctrl+C.</li>
	<li>Opened the design view of table2</li>
	<li>Ctrl+V</li>
</ol>
And there it was, all the columns along with the properties replicated in a jiffy!

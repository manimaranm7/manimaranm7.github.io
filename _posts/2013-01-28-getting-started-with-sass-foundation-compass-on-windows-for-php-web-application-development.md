---
layout: single
title: Getting started with SaSS, Foundation, Compass on Windows, for PHP web application development
date: 2013-01-28 22:53
author: peakbyte
comments: true
categories: [compass, foundation, php, Problem, sass, Solution, Tutorial, webmatrix, windows]
---
My friend wanted to get started with using <a href="http://foundation.zurb.com/">Foundation</a> for an upcoming Greenfield project. The trouble is Foundation comes in two flavours:
<ul>
	<li>Foundation3 with default CSS</li>
	<li>Foundation3 with <a href="http://sass-lang.com/">SCSS</a> (Sassy CSS, which is the syntax used by SASS – "Syntactically Awesome Style Sheets". SASS is an extension of CSS3 which brings familiar programming concepts to CSS like variables, nesting of selectors, functions aka mixins)</li>
</ul>
While "Foundation3 with default CSS" can be perfectly used to take advantage of Foundation's amazing <a href="http://foundation.zurb.com/grid.php">features</a>, using "Foundation3 with SCSS" was thought of a natural way to learn and build websites with SCSS. But, the problem is "Foundation3 with SCSS" does not come as an executable installer for Windows. It is packaged with a CSS Authoring Framework called "<a href="http://compass-style.org/">Compass</a>". For a start, Compass contains re-usable cross-browse CSS mixins, which in itself is a good utility. There are other <a href="http://compass-style.org/reference/compass/">advantages</a> in using Compass too.

The Compass framework does not have a Windows Installer. It is only available as a <a href="http://en.wikipedia.org/wiki/RubyGems">Ruby Gem</a> package, which means we have to install <a href="http://rubyinstaller.org/">Ruby for Windows</a> first. After this, we follow the following steps to get Compass with Foundation:

Start Command Prompt with Ruby (Run as Administrator)

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar1.png" />

Execute the command to install the "Compass with Foundation" package

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar2.png" />

NOTE: If <strong>gem install</strong> throws an ECONNECTION related error, it would mostly to do with the command prompt unable to connect to internet and this could be because the computer may be behind http proxy. In such cases, refer to <strong>gem</strong> documentation on how to use it with –http-proxy option.

Create a new Compass website called "Peakbyte.Web"

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar3.png" />

This creates the following folder structure

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar4.png" />

The detailed structure is better revealed when we open this website using <a href="http://www.microsoft.com/web/webmatrix/">WebMatrix2</a>

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar5.png" />

The <strong>_settings.scss</strong> file contains all the commonly used variables in Foundation. The web developer/designer can either re-use these in their own SCSS by uncommenting the bits as needed.

The <strong>app.scss</strong> file imports the <strong>_settings.scss</strong> file and <strong>the complete foundation</strong> module as shown below

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar6.png" />

The <strong>app.scss </strong>is the main SCSS file. This needs to be processed by the SASS pre-processor to produce <strong>stylesheets/app.css</strong> which is the CSS file referenced in <strong>index.html
</strong>

<strong>So, how does the .scss get processed to .css files? </strong>

By running the following command, the compass SASS pre-processor will continuously watch for any changes done to the .scss files in the "Peakbyte.Web" folder. If it detects any change, it will process the .scss files and re-generate the <strong>stylesheets/app.css</strong> file.

<img alt="" src="http://peakbyte.files.wordpress.com/2013/01/012813_2257_gettingstar7.png" /><strong>
</strong>

So, all that is pending is to <a href="http://pluralsight.com/courses/better-css">learn how to write SCSS</a> and make use of Foundation and Compass modules/features.

<strong>
</strong>

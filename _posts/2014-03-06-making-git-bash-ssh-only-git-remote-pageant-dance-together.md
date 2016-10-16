---
layout: single
title: Making Git Bash, SSH only GIT Remote, Pageant dance together
date: 2014-03-06 16:43
author: peakbyte
comments: true
categories: [Pageant, Problem, PuTTy SSH client, Solution, SSH]
---
Given a SSH only GIT Repo, was unable to git clone the repo, despite my public key being successfully stored in the remote repo's authorization_keys file.

The git clone command invoked from within the git bash kept prompting for password, but could not authenticate for some bizarre reason. Thought it could be some proxy issue. But no, was able to ping successfully to the server hosting the git repo.

Then came the saviour. Pageant.exe, which gets installed when PuTTy SSH client gets installed in windows. Pageant runs on the system tray and serves like a vault of .ppk keys. After adding my ppk to it, was able to successfully connect to the server using putty. Then I thought git clone will also work. But No. Apparently an environment variable GIT_SSH pointing to plink.exe (found within the putty installation directory) is needed. After adding that, I was able to git clone the repository without it prompting me for a password.

So, in summary here are the steps:
<ol>
	<li>Install <a title="PuTTy" href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html" target="_blank">Putty </a>(via Windows Installer to get all the tools in one go)</li>
	<li>Use PuttyGen to create a private/public key pair.</li>
	<li>Send the public key to the remote Git repo administrator so that it can be added to the ~/.ssh/authorization_keys file</li>
	<li>Once that is done, Run Pageant.exe (found in Putty installation directory. Mostly C:/Program Files (x86)/Putty)</li>
	<li>Right-click on the system tray of Pageant to view the keys and add the private key generated using PuttyGen</li>
	<li>Install <a title="Git for Windows" href="http://code.google.com/p/msysgit/downloads/list?q=full+installer+official+git" target="_blank">Git for Windows</a></li>
	<li>Run Git Bash</li>
	<li>Navigate to the Putty installation folder (eg. $ cd "c:\Program Files (x86)\Putty)</li>
	<li>To test if the Pageant is working fine, execute the command $putty git@servername:gittreponame.git</li>
	<li>This will login you to the git server where you can $ cd ~/.ssh to see the authorization_keys file. If curious, to open it, use $cat ~/.ssh/authorization_keys and one of the keys in that would be your public key</li>
	<li>Now try $git clone git@servername:gittreponame.git and it might prompt you for a password. I tried to use the password associated with my private key, but did not work. Hence the following steps.</li>
	<li>Add GIT_SSH environment variable in Windows. The value for this should be the path to plink.exe which will normally be in the Putty installation folder.</li>
</ol>
&nbsp;

&nbsp;

<a href="http://peakbyte.files.wordpress.com/2014/03/git_ssh.png"><img class="alignnone size-medium wp-image-228" alt="git_ssh" src="http://peakbyte.files.wordpress.com/2014/03/git_ssh.png?w=269" width="269" height="300" /></a>

13. Then try $git clone git@servername:gittreponame.git and it should start the cloning without any prompts.

&nbsp;

---
layout: single
title: How to use Ninject IoC with ASP.NET MVC
date: 2009-09-28 23:41
author: peakbyte
comments: true
categories: [Tutorial]
---
<h3>The following are the detailed steps to use Ninject IoC with ASP.NET MVC</h3>
<h5>Download and install TortoiseSVN</h5>
<a href="http://tortoisesvn.tigris.org/" target="_blank">TortoiseSVN</a> is a Subversion client that allows you to manage source control tasks from within Windows Explorer.
<h5>Download the source code for <a href="http://ninject.org/" target="_blank">Ninject</a> from google code</h5>
The Ninject source code is hosted in Google Code website. To download the code to PC, we will use TortoiseSVN. Before that we need the URL of the repository. This is available in the following url:

<a href="http://code.google.com/p/ninject/source/checkout">http://code.google.com/p/ninject/source/checkout</a>

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja1.png"><img style="display:inline;border-width:0;" title="Ninja1" alt="Ninja1" src="http://peakbyte.files.wordpress.com/2009/09/ninja1_thumb.png" width="554" height="330" border="0" /></a>

Then using Windows Explorer use the “Export” option of TortoiseSVN to get a copy of the source code as shown in the figures below:

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja2.png"><img style="display:inline;border-width:0;" title="Ninja2" alt="Ninja2" src="http://peakbyte.files.wordpress.com/2009/09/ninja2_thumb.png" width="554" height="464" border="0" /></a>

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja3.png"><img style="display:inline;border-width:0;" title="Ninja3" alt="Ninja3" src="http://peakbyte.files.wordpress.com/2009/09/ninja3_thumb.png" width="549" height="447" border="0" /></a>

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja4.png"><img style="display:inline;border-width:0;" title="Ninja4" alt="Ninja4" src="http://peakbyte.files.wordpress.com/2009/09/ninja4_thumb.png" width="554" height="269" border="0" /></a>
<h5>Build the Ninject source code</h5>
Once we have the source code, we need to build it to generate the two assemblies we need.

We will run the Build.cmd file that will trigger a Nant build script which will eventually build the entire source.

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja5.png"><img style="display:inline;border-width:0;" title="Ninja5" alt="Ninja5" src="http://peakbyte.files.wordpress.com/2009/09/ninja5_thumb.png" width="554" height="259" border="0" /></a>

Once we have built the source code successfully, we can find the two assemblies we need in the /bin/debug folder as shown below:

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja6.png"><img style="display:inline;border-width:0;" title="Ninja6" alt="Ninja6" src="http://peakbyte.files.wordpress.com/2009/09/ninja6_thumb.png" width="554" height="483" border="0" /></a>
<h5>Create a new MVC project</h5>
Now, let us create a new MVC project using Visual Studio 2008.

<a href="http://peakbyte.files.wordpress.com/2009/09/mvc1.png"><img style="display:inline;border-width:0;" title="MVC1" alt="MVC1" src="http://peakbyte.files.wordpress.com/2009/09/mvc1_thumb.png" width="554" height="455" border="0" /></a>

<a href="http://peakbyte.files.wordpress.com/2009/09/mvc2.png"><img style="display:inline;border-width:0;" title="MVC2" alt="MVC2" src="http://peakbyte.files.wordpress.com/2009/09/mvc2_thumb.png" width="554" height="428" border="0" /></a>

<a href="http://peakbyte.files.wordpress.com/2009/09/mvc3.png"><img style="display:inline;border-width:0;" title="MVC3" alt="MVC3" src="http://peakbyte.files.wordpress.com/2009/09/mvc3_thumb.png" width="335" height="582" border="0" /></a>

Let us test if all is fine by running the application

<a href="http://peakbyte.files.wordpress.com/2009/09/mvc4.png"><img style="display:inline;border-width:0;" title="MVC4" alt="MVC4" src="http://peakbyte.files.wordpress.com/2009/09/mvc4_thumb.png" width="554" height="398" border="0" /></a>
<h5>Making the MVC project a meaningful project</h5>
Before jumping into adding references to the Ninject assemblies, let us modify this MVC project to do something useful.

We are going to create an application that will help us browse through the bills in a Parliament. The Parliament has two chambers. House of Lords and House of Commons and each have their own bills at anytime which they are legislating about.

I am going to show only the code relevant to this topic, so will not show in detail all the steps in creating this. The source code for this can be downloaded to view the complete implementation minus Ninject integration. Some screen shots of the application is shown below:
<h6>Home Page</h6>
<a href="http://peakbyte.files.wordpress.com/2009/09/parl1.png"><img style="display:inline;border-width:0;" title="Parl1" alt="Parl1" src="http://peakbyte.files.wordpress.com/2009/09/parl1_thumb.png" width="554" height="398" border="0" /></a>
<h6>Bills page</h6>
<a href="http://peakbyte.files.wordpress.com/2009/09/parl2.png"><img style="display:inline;border-width:0;" title="Parl2" alt="Parl2" src="http://peakbyte.files.wordpress.com/2009/09/parl2_thumb.png" width="554" height="398" border="0" /></a>
<h6>Bills in House of Lords</h6>
<a href="http://peakbyte.files.wordpress.com/2009/09/parl3.png"><img style="display:inline;border-width:0;" title="Parl3" alt="Parl3" src="http://peakbyte.files.wordpress.com/2009/09/parl3_thumb.png" width="554" height="398" border="0" /></a>
<h6>Bills in House of Commons</h6>
<a href="http://peakbyte.files.wordpress.com/2009/09/parl4.png"><img style="display:inline;border-width:0;" title="Parl4" alt="Parl4" src="http://peakbyte.files.wordpress.com/2009/09/parl4_thumb.png" width="554" height="398" border="0" /></a>

The following shown the Solution Explorer highlighting the Code Files needed to accomplish the above application.

<a href="http://peakbyte.files.wordpress.com/2009/09/mvc5.png"><img style="display:inline;border-width:0;" title="MVC5" alt="MVC5" src="http://peakbyte.files.wordpress.com/2009/09/mvc5_thumb.png" width="335" height="728" border="0" /></a>
<h5>The case for Dependency Injection</h5>
The List of Bills displayed in the website is at the moment “fake” data coming from a class called “FakeDepository”.
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:752d7344-6128-42ea-a188-4baeb3331f57" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">namespace</span><span style="background:#181818;color:#fef1a9;">JoeBloggsStore</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">DataModel</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Concrete</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">class</span><span style="background:#181818;color:#c7c7f1;">FakeDataRepository</span><span style="background:#181818;color:#e0e0e0;"> : </span><span style="background:#181818;color:#c7c7f1;">IDataRepository</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#c080c0;">// fake list of bills in house of lords</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">private</span><span style="background:#181818;color:#8080c0;">static</span><span style="background:#181818;color:#c7c7f1;">IQueryable</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt; </span><span style="background:#181818;color:#fef1a9;">lordsBills</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">List</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt;{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#60ff60;">"Live Music Bill [HL]"</span><span style="background:#181818;color:#e0e0e0;">,</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#60ff60;">"Constitutional Reform Bill [HL]"</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }.</span><span style="background:#181818;color:#fef1a9;">AsQueryable</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#c080c0;">// fake list of bills in house of commons</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">private</span><span style="background:#181818;color:#8080c0;">static</span><span style="background:#181818;color:#c7c7f1;">IQueryable</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt; </span><span style="background:#181818;color:#fef1a9;">commonsBills</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">List</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt;{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#60ff60;">"Maximum Wage Bill"</span><span style="background:#181818;color:#e0e0e0;">,</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#60ff60;">"Bankers' Pensions (Limits) Bill"</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }.</span><span style="background:#181818;color:#fef1a9;">AsQueryable</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">IQueryable</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt; </span><span style="background:#181818;color:#fef1a9;">LordsBills</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">get</span><span style="background:#181818;color:#e0e0e0;"> { </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">lordsBills</span><span style="background:#181818;color:#e0e0e0;">; }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">IQueryable</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#8080c0;">string</span><span style="background:#181818;color:#e0e0e0;">&gt; </span><span style="background:#181818;color:#fef1a9;">CommonsBills</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">get</span><span style="background:#181818;color:#e0e0e0;"> { </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">commonsBills</span><span style="background:#181818;color:#e0e0e0;">; }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">}</span></li>
</ol>
</div>
</div>
</div>
At the moment, although we have based this class on an interface, we are using this in a tightly-coupled fashion in the “BillController” as shown below:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:579020c2-5ed1-45c0-826c-33a9e0e3a294" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">ActionResult</span><span style="background:#181818;color:#fef1a9;">Lords</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"House"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#60ff60;">"Lords"</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"Bills"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">FakeDataRepository</span><span style="background:#181818;color:#e0e0e0;">().</span><span style="background:#181818;color:#fef1a9;">LordsBills</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">ToList</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">View</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">ActionResult</span><span style="background:#181818;color:#fef1a9;">Commons</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"House"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#60ff60;">"Commons"</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"Bills"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">FakeDataRepository</span><span style="background:#181818;color:#e0e0e0;">().</span><span style="background:#181818;color:#fef1a9;">CommonsBills</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">ToList</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">View</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
</ol>
</div>
</div>
</div>
This is not a good practice to Program to an implementation (Line 4 and Line 10 in Figure). Instead, we should be Programming to an interface and make use loose-coupling where ever applicable.
<h5>Programming to an Interface</h5>
The following code shows the modified BillController that takes in an IDataRepository in it’s constructor. (Lines 5 up to 10 in Figure)

The interface variable “dataRepository” is then used to get the Bills (Line 24 and 30 in Figure)
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:5789b501-27a0-40be-ba0d-0c34a0e42daf" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">namespace</span><span style="background:#181818;color:#fef1a9;">JoeBloggsStore</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Controllers</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">class</span><span style="background:#181818;color:#c7c7f1;">BillController</span><span style="background:#181818;color:#e0e0e0;"> : </span><span style="background:#181818;color:#c7c7f1;">Controller</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">private</span><span style="background:#181818;color:#c7c7f1;">IDataRepository</span><span style="background:#181818;color:#fef1a9;">dataRepository</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#fef1a9;">BillController</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#c7c7f1;">IDataRepository</span><span style="background:#181818;color:#fef1a9;">repos</span><span style="background:#181818;color:#e0e0e0;">)</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">this</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">dataRepository</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#fef1a9;">repos</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#c080c0;">//</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#c080c0;">// GET: /Bill/</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">ActionResult</span><span style="background:#181818;color:#fef1a9;">Index</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"House"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#60ff60;">"Parliament"</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"Bills"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#8080c0;">null</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">View</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">ActionResult</span><span style="background:#181818;color:#fef1a9;">Lords</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"House"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#60ff60;">"Lords"</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"Bills"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#8080c0;">this</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">dataRepository</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">LordsBills</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">ToList</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">View</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#c7c7f1;">ActionResult</span><span style="background:#181818;color:#fef1a9;">Commons</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"House"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#60ff60;">"Commons"</span><span style="background:#181818;color:#e0e0e0;">;</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">ViewData</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"Bills"</span><span style="background:#181818;color:#e0e0e0;">] = </span><span style="background:#181818;color:#8080c0;">this</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">dataRepository</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">CommonsBills</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">ToList</span><span style="background:#181818;color:#e0e0e0;">();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#fef1a9;">View</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">}</span></li>
</ol>
</div>
</div>
</div>
But, who is going to pass in the correct IDataRepository instance to the BillController. This is where Ninject comes in.
<h5>Integrating Ninject for Constructor Injection</h5>
The BillController depends on an appropriate instance of IDataRepository to be passed when it’s constructed using the constructor. By default, MVC Framework creates an instance of BillController by using a parameterless constructor. In our case, we have want MVC to call our constructor with IDataRepository parameter and pass in the correct instance that we will configure.

To instruct the MVC framework to do this, we have to modify the Global.asax.cs. The default Global.asax.cs file is as follows:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:57b92842-bf7d-4c93-a481-ee4b6534df1c" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">namespace</span><span style="background:#181818;color:#fef1a9;">JoeBloggsStore</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#c080c0;">// Note: For instructions on enabling IIS6 or IIS7 classic mode, </span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#c080c0;">// visit http://go.microsoft.com/?LinkId=9394801</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">class</span><span style="background:#181818;color:#c7c7f1;">MvcApplication</span><span style="background:#181818;color:#e0e0e0;"> : </span><span style="background:#181818;color:#fef1a9;">System</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Web</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#c7c7f1;">HttpApplication</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">static</span><span style="background:#181818;color:#8080c0;">void</span><span style="background:#181818;color:#fef1a9;">RegisterRoutes</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#c7c7f1;">RouteCollection</span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">)</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">IgnoreRoute</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"{resource}.axd/{*pathInfo}"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">MapRoute</span><span style="background:#181818;color:#e0e0e0;">(</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#60ff60;">"Default"</span><span style="background:#181818;color:#e0e0e0;">,                                              </span><span style="background:#181818;color:#c080c0;">// Route name</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#60ff60;">"{controller}/{action}/{id}"</span><span style="background:#181818;color:#e0e0e0;">,                           </span><span style="background:#181818;color:#c080c0;">// URL with parameters</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#e0e0e0;"> { </span><span style="background:#181818;color:#fef1a9;">controller</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">"Home"</span><span style="background:#181818;color:#e0e0e0;">, </span><span style="background:#181818;color:#fef1a9;">action</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">, </span><span style="background:#181818;color:#fef1a9;">id</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">""</span><span style="background:#181818;color:#e0e0e0;"> }  </span><span style="background:#181818;color:#c080c0;">// Parameter defaults</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            );</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">protected</span><span style="background:#181818;color:#8080c0;">void</span><span style="background:#181818;color:#fef1a9;">Application_Start</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">RegisterRoutes</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#c7c7f1;">RouteTable</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Routes</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">}</span></li>
</ol>
</div>
</div>
</div>
We need to first make the MvcApplication derive from “Ninject.Framework.Mvc.NinjectHttpApplication” as shown below:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:1e91293e-79a8-4d09-891e-4323c6880d66" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;margin:0 0 0 2em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">class</span><span style="background:#181818;color:#c7c7f1;">MvcApplication</span><span style="background:#181818;color:#e0e0e0;"> : </span><span style="background:#181818;color:#fef1a9;">Ninject</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Framework</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Mvc</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#c7c7f1;">NinjectHttpApplication</span></li>
</ol>
</div>
</div>
</div>
To do this, we need to add two references to our project. Before that let us copy the two assemblies we need to a “lib” folder inside our Visual Studio solution folder:

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja61.png"><img style="display:inline;border-width:0;" title="Ninja6" alt="Ninja6" src="http://peakbyte.files.wordpress.com/2009/09/ninja6_thumb1.png" width="554" height="483" border="0" /></a>

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja7.png"><img style="display:inline;border-width:0;" title="Ninja7" alt="Ninja7" src="http://peakbyte.files.wordpress.com/2009/09/ninja7_thumb.png" width="554" height="157" border="0" /></a>

Let us then add the references:

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja8.png"><img style="display:inline;border-width:0;" title="Ninja8" alt="Ninja8" src="http://peakbyte.files.wordpress.com/2009/09/ninja8_thumb.png" width="554" height="449" border="0" /></a>

Upon adding the reference, the NinjectHttpApplication requires us to implement two Abstract members
<ol>
	<li>CreateKernel()</li>
	<li>RegisterRoutes(RouteCollection)</li>
</ol>
The CreateKernel is where we tell Ninject which Concrete Class needs to be injected when the Constructor of BillController is called.

The RegisterRoutes is where we configure the MVC Routing options.

We need to do two things now:
<ol>
	<li>Ensure the Routing still works (because the Application_Start() is now moved into NinjectHttpApplication and RegisterRoutes is also made abstract in NinjectHttpApplication)</li>
	<li>Create a configuration that tells Ninject to inject FakeDepository whenever IDataRepository is requested.</li>
</ol>
First, change the RegisterRoutes from being a private method to an overridden protected method  as shown below:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:6c467edb-2fc9-4d47-99c8-78a7bbac9e2d" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">protected</span><span style="background:#181818;color:#8080c0;">override</span><span style="background:#181818;color:#8080c0;">void</span><span style="background:#181818;color:#fef1a9;">RegisterRoutes</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#c7c7f1;">RouteCollection</span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">)</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">IgnoreRoute</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"{resource}.axd/{*pathInfo}"</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">routes</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">MapRoute</span><span style="background:#181818;color:#e0e0e0;">(</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#60ff60;">"Default"</span><span style="background:#181818;color:#e0e0e0;">,                                              </span><span style="background:#181818;color:#c080c0;">// Route name</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#60ff60;">"{controller}/{action}/{id}"</span><span style="background:#181818;color:#e0e0e0;">,                           </span><span style="background:#181818;color:#c080c0;">// URL with parameters</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">                </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#e0e0e0;"> { </span><span style="background:#181818;color:#fef1a9;">controller</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">"Home"</span><span style="background:#181818;color:#e0e0e0;">, </span><span style="background:#181818;color:#fef1a9;">action</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">"Index"</span><span style="background:#181818;color:#e0e0e0;">, </span><span style="background:#181818;color:#fef1a9;">id</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#60ff60;">""</span><span style="background:#181818;color:#e0e0e0;"> }  </span><span style="background:#181818;color:#c080c0;">// Parameter defaults</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            );</span></li>
	<li></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
</ol>
</div>
</div>
</div>
Now, the configuration to Ninject is provided by creating a Module that derives from  Ninject.Core.StandardModule (There are other modules which we will not delve into now)

The following code shows such a Module:

<a href="http://peakbyte.files.wordpress.com/2009/09/ninja9.png"><img style="display:inline;border-width:0;" title="Ninja9" alt="Ninja9" src="http://peakbyte.files.wordpress.com/2009/09/ninja9_thumb.png" width="335" height="728" border="0" /></a>
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:a9a07423-8ddc-40a9-883d-859a5c298625" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2.5em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#8080c0;">namespace</span><span style="background:#181818;color:#fef1a9;">JoeBloggsStore</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">{</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">class</span><span style="background:#181818;color:#c7c7f1;">WebModule</span><span style="background:#181818;color:#e0e0e0;"> : </span><span style="background:#181818;color:#c7c7f1;">StandardModule</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">override</span><span style="background:#181818;color:#8080c0;">void</span><span style="background:#181818;color:#fef1a9;">Load</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">Bind</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#c7c7f1;">IDataRepository</span><span style="background:#181818;color:#e0e0e0;">&gt;().</span><span style="background:#181818;color:#fef1a9;">To</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#c7c7f1;">FakeDataRepository</span><span style="background:#181818;color:#e0e0e0;">&gt;().</span><span style="background:#181818;color:#fef1a9;">Using</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#c7c7f1;">OnePerRequestBehavior</span><span style="background:#181818;color:#e0e0e0;">&gt;();            </span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">    }</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">}</span></li>
</ol>
</div>
</div>
</div>
The Line 7 in above Figure says, “Ninject, please provide one instance of FakeDataRepository per Request whenever IDataRepository is needed”.

We have to now use this WebModule  in CreateKernel function in Global.asax.cs as shown below:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:66068a01-49be-41e8-8d3a-24b49486e28b" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">protected</span><span style="background:#181818;color:#8080c0;">override</span><span style="background:#181818;color:#fef1a9;">Ninject</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">Core</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#c7c7f1;">IKernel</span><span style="background:#181818;color:#fef1a9;">CreateKernel</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#c7c7f1;">IModule</span><span style="background:#181818;color:#e0e0e0;">[] </span><span style="background:#181818;color:#fef1a9;">modules</span><span style="background:#181818;color:#e0e0e0;"> = </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">IModule</span><span style="background:#181818;color:#e0e0e0;">[] { </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">AutoControllerModule</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#c7c7f1;">Assembly</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">GetExecutingAssembly</span><span style="background:#181818;color:#e0e0e0;">()), </span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">WebModule</span><span style="background:#181818;color:#e0e0e0;">() };</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#8080c0;">return</span><span style="background:#181818;color:#8080c0;">new</span><span style="background:#181818;color:#c7c7f1;">StandardKernel</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#fef1a9;">modules</span><span style="background:#181818;color:#e0e0e0;">);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
</ol>
</div>
</div>
</div>
If we try to build and run this code, we might get an error saying “OnePerRequestModule has not been loaded”.

This is because we have told which assembly contains this HttpModule. We can do this in the &lt;httpModules&gt; section of the web.config:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:e229b7ee-bc9d-43db-8538-9a7b5441d954" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#5f5fd8;">    &lt;httpModules&gt;</span></li>
	<li><span style="background:#181818;color:#5f5fd8;">      &lt;add </span><span style="background:#181818;color:#c7c7f1;">name</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"ScriptModule"</span><span style="background:#181818;color:#c7c7f1;">type</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"System.Web.Handlers.ScriptModule, System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"</span><span style="background:#181818;color:#5f5fd8;">/&gt;</span></li>
	<li><span style="background:#181818;color:#5f5fd8;">      &lt;add </span><span style="background:#181818;color:#c7c7f1;">name</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"UrlRoutingModule"</span><span style="background:#181818;color:#c7c7f1;">type</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"System.Web.Routing.UrlRoutingModule, System.Web.Routing, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"</span><span style="background:#181818;color:#5f5fd8;"> /&gt;</span></li>
	<li><span style="background:#181818;color:#5f5fd8;">      &lt;add </span><span style="background:#181818;color:#c7c7f1;">name</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"OnePerRequestModule"</span><span style="background:#181818;color:#c7c7f1;">type</span><span style="background:#181818;color:#5f5fd8;">=</span><span style="background:#181818;color:#60ff60;">"Ninject.Core.Behavior.OnePerRequestModule, Ninject.Core"</span><span style="background:#181818;color:#5f5fd8;">/&gt;</span></li>
	<li><span style="background:#181818;color:#5f5fd8;">    &lt;/httpModules&gt;</span></li>
</ol>
</div>
</div>
</div>
If we run the application now, we should see the application working as expected.

In the future when we want to get the data from a SQL Server database, we can create a new class called SQLDataRepository. The possibilities of SQLDataRepository requiring a connectionString to the database is high. So, this can be configured in the WebModule as follows:
<div class="wlWriterEditableSmartContent" id="scid:9ce6104f-a9aa-4a17-a79f-3a39532ebf7c:cecbfdff-bbb6-49de-9170-0499cf6997b2" style="display:inline;float:none;margin:0;padding:0;">
<div style="border:#000080 1px solid;font-family:'Courier New', Courier, Monospace;font-size:10pt;">
<div style="background:#000080;color:#fff;font-family:Verdana, Tahoma, Arial, sans-serif;font-weight:bold;padding:2px 5px;">Code Snippet</div>
<div style="background:#ddd;max-height:300px;overflow:auto;">
<ol style="background:#000000;white-space:nowrap;margin:0 0 0 2em;padding:0 0 0 5px;">
	<li><span style="background:#181818;color:#e0e0e0;">        </span><span style="background:#181818;color:#8080c0;">public</span><span style="background:#181818;color:#8080c0;">override</span><span style="background:#181818;color:#8080c0;">void</span><span style="background:#181818;color:#fef1a9;">Load</span><span style="background:#181818;color:#e0e0e0;">()</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        {</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#c080c0;">//Bind&lt;IDataRepository&gt;().To&lt;FakeDataRepository&gt;().Using&lt;OnePerRequestBehavior&gt;();</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">            </span><span style="background:#181818;color:#fef1a9;">Bind</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#c7c7f1;">IDataRepository</span><span style="background:#181818;color:#e0e0e0;">&gt;().</span><span style="background:#181818;color:#fef1a9;">To</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#fef1a9;">SQLDataRepository</span><span style="background:#181818;color:#e0e0e0;">&gt;().</span><span style="background:#181818;color:#fef1a9;">Using</span><span style="background:#181818;color:#e0e0e0;">&lt;</span><span style="background:#181818;color:#c7c7f1;">OnePerRequestBehavior</span><span style="background:#181818;color:#e0e0e0;">&gt;().</span><span style="background:#181818;color:#fef1a9;">WithConstructorArgument</span><span style="background:#181818;color:#e0e0e0;">(</span><span style="background:#181818;color:#60ff60;">"connectionString"</span><span style="background:#181818;color:#e0e0e0;">, </span><span style="background:#181818;color:#c7c7f1;">WebConfigurationManager</span><span style="background:#181818;color:#e0e0e0;">.</span><span style="background:#181818;color:#fef1a9;">ConnectionStrings</span><span style="background:#181818;color:#e0e0e0;">[</span><span style="background:#181818;color:#60ff60;">"ApplicationServices"</span><span style="background:#181818;color:#e0e0e0;">]);</span></li>
	<li><span style="background:#181818;color:#e0e0e0;">        }</span></li>
</ol>
</div>
</div>
</div>
The SQLDataRepository’s Constructor should obviously take a connectionstring as parameter for this to work.

The source code for completed web application is available for <a title="Source Code Download" href="http://www.manivannan.org/Resources/BlogFiles/JoeBloggsStore.zip" target="_blank">download</a>.

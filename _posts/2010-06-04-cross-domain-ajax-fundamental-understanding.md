---
layout: single
title: Cross-Domain, Ajax Fundamental understanding
date: 2010-06-04 11:02
author: peakbyte
comments: true
categories: [FX.Web.ASPNET, Problem, Solution]
---
<p>I had promised my students that we would implement a “Find nearest XXXX” feature in our on going project. I was doing this for the first time and thought it would not be difficult. But, most of my time while preparing for the class, I was frustrated. </p>  <p>I could not come up with a WCF Web Service (hosted on Visual Studio’s development web server eg., http://localhost:1234/MyService.svc ) that could be invoked by Javascript on my website (hosted again on Visual Studio’s development web server eg., http://localhost:9876/MyWebsite/Default.aspx ).</p>  <p>Due to time constraints, I abandoned the WCF Service implementation and went in for the <a href="http://encosia.com/2008/05/29/using-jquery-to-directly-call-aspnet-ajax-page-methods/" target="_blank">ASP.NET Ajax Page Methods</a></p>  <p>It’s only after reading this nice article, I understand the mistake I made or the way the cross-domain web requests work.</p>  <p><a href="http://dotnetslackers.com/columns/ajax/MashitUpwithASPNETAJAX.aspx" target="_blank">Mash-it Up with ASP.NET AJAX: Using a proxy to access remote API</a></p>

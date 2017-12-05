---
layout: post
status: publish
published: true
title: OWASP Testing Methodology
author:
  display_name: ethicalhack3r
  login: ethicalhack3r
  email: ryandewhurst@gmail.com
  url: ''
author_login: ethicalhack3r
author_email: ryandewhurst@gmail.com
excerpt: "It is very easy for some one to find an XSS vulnerability within a web application
  and write a report about it. According to <a href=\"http://www.whitehatsec.com/home/assets/WPStatsreport_100107.pdf\">WhiteHat
  Security</a> (2007) there is a 73% chance that you will find an XSS vulnerability
  within a web application. Does finding one of these mean you have assessed the security
  of the web application? Let's take a web application vulnerability that is 'seen'
  to be more critical. Again, according to <a href=\"http://www.whitehatsec.com/home/assets/WPStatsreport_100107.pdf\">WhiteHat
  Security</a> you have a 18% likelihood to find an SQL Injection vulnerability within
  a web application. So during the web application security assessment you have found
  an SQL injection vulnerability, the back end DBMS is a version of Microsoft SQL
  Server which has '<a href=\"http://msdn.microsoft.com/en-us/library/ms175046.aspx\">xp_cmdshell</a>'
  enabled by default. You manage to get a reverse shell and acquire a copy of the
  database. Great! By gaining shell access to the server does that mean you have properly
  assessed the security of the web application? No!\r\n\r\n"
wordpress_id: 614
wordpress_url: http://www.ethicalhack3r.co.uk/?p=614
date: '2010-03-08 13:47:38 +0000'
date_gmt: '2010-03-08 13:47:38 +0000'
---
<p>It is very easy for some one to find an XSS vulnerability within a web application and write a report about it. According to <a href="http://www.whitehatsec.com/home/assets/WPStatsreport_100107.pdf">WhiteHat Security</a> (2007) there is a 73% chance that you will find an XSS vulnerability within a web application. Does finding one of these mean you have assessed the security of the web application? Let's take a web application vulnerability that is 'seen' to be more critical. Again, according to <a href="http://www.whitehatsec.com/home/assets/WPStatsreport_100107.pdf">WhiteHat Security</a> you have a 18% likelihood to find an SQL Injection vulnerability within a web application. So during the web application security assessment you have found an SQL injection vulnerability, the back end DBMS is a version of Microsoft SQL Server which has '<a href="http://msdn.microsoft.com/en-us/library/ms175046.aspx">xp_cmdshell</a>' enabled by default. You manage to get a reverse shell and acquire a copy of the database. Great! By gaining shell access to the server does that mean you have properly assessed the security of the web application? No!</p>
<p><a id="more"></a><a id="more-614"></a></p>
<p>So let's say that the person who found the SQL injection vulnerability left it at that and wrote his report and got a pat on the back. What happens to the other possible vulnerabilities which may affect the web application, including further SQL injection?! As you can see by just finding one or two or ten vulnerabilities within a web application does not mean it has been a thorough assessment. It's not about how many, it's about the quality of the test. That's where methodologies come in. </p>
<p>Methodologies are peer reviewed industry <strong><em>guidelines</em></strong> on how a test should be carried out. There is no silver bullet when it comes to security, every web application is different. However these guidelines can help us to ensure that we have done a thorough test, as always, thinking out side of the box is encouraged. There is a danger when using methodologies and check lists that you stick to them word for word and do not sway from them. As long as your aware of this danger you should be fine.</p>
<p><strong>What is the OWASP Testing Methodology?</strong><br />
The OWASP testing methodology is defined in the <a href="http://www.owasp.org/index.php/Category:OWASP_Testing_Project">OWASP Testing Guide v.3.0</a>.</p>
<p><img src="http://www.ethicalhack3r.co.uk/wp-content/uploads/2010/03/detail_5691953.jpg" alt="" title="detail_5691953" width="108" height="140" class="alignnone size-full wp-image-618" /></p>
<blockquote><p>Penetration testing will never be an exact science where a complete list of all possible issues that should be tested can be defined. Indeed, penetration testing is only an appropriate technique for testing the security of web applications under certain circumstances. The goal is to collect all the possible testing techniques, explain them and keep the guide updated. The OWASP Web Application Penetration Testing method is based on the black box approach.</p></blockquote>
<p>The OWASP Testing Methodology divides the test into two parts, passive mode and active mode.</p>
<blockquote><p><strong>Passive mode:</strong> in the passive mode, the tester tries to understand the application's logic, and plays with the application. Tools can be used for information gathering, for example, an HTTP proxy to observe all the HTTP requests and responses. At the end of this phase, the tester should understand all the access points (gates) of the application (e.g., HTTP headers, parameters, and cookies).</p></blockquote>
<p>The <strong>active mode</strong> is split in to 9 sub-categories for a total of 66 controls:</p>
<p>Configuration Management Testing<br />
Business Logic Testing<br />
Authentication Testing<br />
Authorization testing<br />
Session Management Testing<br />
Data Validation Testing<br />
Denial of Service Testing<br />
Web Services Testing<br />
Ajax Testing</p>
<p>Each control is a particular test that should be carried out and has a unique reference number. The OWASP Testing Guide v3.0 lists all 66 controls which should be tested and how to test for them. Of course, all of these tests can not always be carried out. Some times they are just not applicable because that particular functionality is not present within the web application or you may not want to try some of the DoS tests on a live environment.</p>
<p>So in my opinion to carry out a thorough and quality web application security assessment, you need a methodology, the ability to think outside of the box, automated and manual techniques, persistence and a love for the job.</p>
<p>The OWASP Testing Guide v.3.0 is one of my favourite books when it comes to web application assessments. You can download the free PDF version or buy the very reasonable priced paper back from lulu.com. For further details on the guide visit the projects home page:<br />
<a href="http://www.owasp.org/index.php/Category:OWASP_Testing_Project" target="_blank">http://www.owasp.org/index.php/Category:OWASP_Testing_Project</a></p>

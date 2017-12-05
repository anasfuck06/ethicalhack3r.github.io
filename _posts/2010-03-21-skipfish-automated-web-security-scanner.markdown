---
layout: post
status: publish
published: true
title: Skipfish - Automated web security scanner
author:
  display_name: ethicalhack3r
  login: ethicalhack3r
  email: ryandewhurst@gmail.com
  url: ''
author_login: ethicalhack3r
author_email: ryandewhurst@gmail.com
excerpt: "A couple of days ago (March 19th) Michal Zalewski famous for tools such
  as p0f and his excellent book 'Silence on the wire' announced the release of an
  open source automated web security scanner called Skipfish from the <a href=\"http://googleonlinesecurity.blogspot.com/\">Google
  Online Security Blog</a>.\r\n\r\n<strong>\r\n</strong>\r\n\r\n<img src=\"http://www.ethicalhack3r.co.uk/wp-content/uploads/2010/03/sf_name.png\"
  alt=\"\" title=\"sf_name\" width=\"203\" height=\"93\" class=\"alignnone size-full
  wp-image-638\" />\r\n\r\n<strong>\r\n</strong>\r\n\r\n<blockquote>Key features:\r\n\r\n<strong>High
  speed:</strong> pure C code, highly optimized HTTP handling, minimal CPU footprint
  - easily achieving 2000 requests per second with responsive targets. \r\n\r\n<strong>Ease
  of use:</strong> heuristics to support a variety of quirky web frameworks and mixed-technology
  sites, with automatic learning capabilities, on-the-fly wordlist creation, and form
  autocompletion. \r\n\r\n<strong>Cutting-edge security logic:</strong> high quality,
  low false positive, differential security checks, capable of spotting a range of
  subtle flaws, including blind injection vectors. </blockquote>"
wordpress_id: 633
wordpress_url: http://www.ethicalhack3r.co.uk/?p=633
date: '2010-03-21 02:49:44 +0000'
date_gmt: '2010-03-21 02:49:44 +0000'
---
<p>A couple of days ago (March 19th) Michal Zalewski famous for tools such as p0f and his excellent book 'Silence on the wire' announced the release of an open source automated web security scanner called Skipfish from the <a href="http://googleonlinesecurity.blogspot.com/" target="_blank">Google Online Security Blog</a>.</p>
<p><img src="http://www.ethicalhack3r.co.uk/wp-content/uploads/2010/03/sf_name.png" alt="" title="sf_name" width="203" height="93" class="alignnone size-full wp-image-638" /></p>
<blockquote><p>Key features:</p>
<p><strong>High speed:</strong> pure C code, highly optimized HTTP handling, minimal CPU footprint - easily achieving 2000 requests per second with responsive targets. </p>
<p><strong>Ease of use:</strong> heuristics to support a variety of quirky web frameworks and mixed-technology sites, with automatic learning capabilities, on-the-fly wordlist creation, and form autocompletion. </p>
<p><strong>Cutting-edge security logic:</strong> high quality, low false positive, differential security checks, capable of spotting a range of subtle flaws, including blind injection vectors. </p></blockquote>
<p><a id="more"></a><a id="more-633"></a></p>
<p>Skipfish works from dictionary files with the .wl extention. According to Skipfish these dictionaries are of critical importance to the quality of your scans. Each entry in the dictionary is either an extension (e) or wordlist (w).The dictionaries are used for "When a new directory, or a file-like query or POST parameter is discovered, the scanner attempts passing all possible <keyword> values to discover new files, directories, etc."</p>
<p>Naturally I ran Skipfish against DVWA to see how it performed and to see how many vulnerabilities it picked up. The first time I run it against DVWA I used the following command: "./skipfish -A admin:password -C security=low -o /home/user/Desktop/skipfish_dvwa -W /home/user/Desktop/skipfish/dictionaries/default.wl http://127.0.0.1/dvwa/login.php".</p>
<p>The command above is supplying the DVWA HTTP Form username and password (-A admin:password), setting the cookie (-C security=low), giving the output directory (-o /home/user/Desktop/skipfish_dvwa), selecting the default dictionary (-W /home/user/Desktop/skipfish/dictionaries/default.wl) and finally selecting the target (http://127.0.0.1/dvwa/login.php).</p>
<p>50 million requests and 24 hours later Skipfish was still going. At first I thought this may have been how Skipfish worked and started Tweeting about my findings. I ran some further tests, this time limiting the depth of links Skipfish would follow to 3 and limiting the requests to 1 million. Skipfish now completed the scan within about 20 minutes however the scan was not very thorough.</p>
<p>The Skipfish reports are HTML based and are quite user friendly. Skipfish not only picked up lot's of useful information however also found some critical vulnerabilities within another live web application I tested it against.</p>
<p>After noticing my Tweets Michal got in contact via email to offer me his help. He noted that the first scan was not normal Skipfish behaviour and helped with debugging. I plan to try and replicate the first scans behaviour during this coming week and send Michal the logs for him to debug.</p>
<p>All in all despite the first attempt, Skipfish found some very useful information which some other scanners I run did not pick up. I plan to use it further in future to try and understand and judge its performance better.</p>
<p>A big thanks to Michal for getting in contact and helping me out with debugging! =)</p>
<p>To download Skipfish: <a href="http://code.google.com/p/skipfish/" target="_blank">http://code.google.com/p/skipfish/</a> (don't forget to comment on your experience!)</keyword></p>

---
layout: post
title: Clean flash vs Dirty flash – Custom ROM’s
category: Android
tags: android
year: 2015
month: 02
day: 22
published: true
description: This post will help you learn the difference between a clean and a dirty flash done while installing newer versions of custom ROM's.

---

<div class="row">	
	<div class="span9 columns">
		<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html>
<head>
  <meta content="text/html; charset=ISO-8859-1"
 http-equiv="content-type">
  <title></title>
</head>
<body>
<p class="MsoNormal">Clean flash:<o:p></o:p></p>
<p class="MsoListParagraphCxSpFirst"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">1.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Install
Titanium Backup. Open Titanium Backup
&gt; Go to menu &gt; Batch actions &gt; Backup apps +
system data. This will
backup all your user apps, app data and all the things like wifi
passwords,
calendar events, etc. This will not backup system apps, as that mostly
will<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">2.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Go to
TWRP recovery (or whichever custom
recovery you are using) and do a Factory reset. This will clear cache,
user
apps and data that those apps were using. The data (images, movies,
music, etc.)
that you have in your internal/external SD card/storage will remain
intact.<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">3.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->In
the TWRP recovery, flash the new ROM files in
the following sequence: Firmware update (if any) &gt; Custom ROM
&gt; GAPPS
&gt; Custom Kernel (if any). Then wipe Dalvik/Cache.<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">4.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]--><span
 style=""></span>Reboot
system.<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">5.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Do
initial system setup (skip restoring your
apps via Google account).<o:p></o:p></p>
<p class="MsoListParagraphCxSpLast"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">6.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Install
Titanium backup. Restore user apps +
data.<o:p></o:p></p>
<p class="MsoNormal">Dirty Flash:<o:p></o:p></p>
<p class="MsoListParagraphCxSpFirst"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">1.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Go to
TWRP. Clear cache/Dalvik.<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">2.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->In
the TWRP recovery, flash the new ROM files in
the following sequence: Firmware update (if any) &gt; Custom ROM
&gt; GAPPS
&gt; Custom Kernel (if any).<o:p></o:p></p>
<p class="MsoListParagraphCxSpLast"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">3.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Reboot
system.<o:p></o:p></p>
<p class="MsoNormal"><o:p>&nbsp;</o:p></p>
</body>
</html>
		
	</div>
</div> 
		
		
		
		
		

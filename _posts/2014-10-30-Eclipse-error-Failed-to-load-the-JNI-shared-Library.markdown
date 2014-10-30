---
layout: post
title: Eclipse error: Failed to load the JNI shared Library
category: Java
tags: Eclipse Java
year: 2014
month: 10
day: 30
published: true
description: This error might come when you are opening the Eclipse for Java in your system for the first time.

---

<div class="row">	
	<div class="span9 columns">
		<p>This error mostly comes up when you have multiple JRE's or JDK's installed on your system and some of them don't match your processor type 64/32 Bit. Ideally your setup for a 64 bit system should be:</p>
		<ul>
			<li>64-bit</li>
			<li>OS 64-bit Java</li>
			<li>64-bit Eclipse</li>
		</ul>
		<p>But since you are getting this error then that's not the case. To fix this go to your eclipse folder open the eclipse.ini file. It will look somewhat like this:</p>
		<script src="https://gist.github.com/ajgupta/f600f144ea863b89d9b0.js"></script>
		<p>To fix it you just need to add the <b>path where you installed JDK</b> which you want to use (64Bit JDK for 64Bit OS). Like this:</p>
		<script src="https://gist.github.com/ajgupta/3bdaf5d20f5e53c18b4d.js"></script>
		<p>After adding this your eclipse.ini file should look like this:</p>
		<script src="https://gist.github.com/ajgupta/05ad9b153ca71dd2b013.js"></script>
		<p>Save the changes in eclipse.ini. This should fix the issue and you should be able to run Eclipse.</p>
	</div>
</div> 
		
		
		
		
		

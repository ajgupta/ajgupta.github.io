---
layout: post
title: Completely remove Java from Ubuntu 14.04
category: Ubuntu
tags: Ubuntu Java
year: 2014
month: 09
day: 18
published: true
description: Run the following commands in the terminal one by one to completely uninstall Java and related components from your Ubuntu 14.04 system.

---

<div class="row">	
	<div class="span9 columns">
		<p>There maybe many reasons why you might want to remove Java from your system (mine was tthe continious updates, even though Java wasn't very useful for my work). Whatever the resons, follow the procedure below to uninstall Java from your Ubuntu 14.04 system:</p>
		<h2>Remove all the Java related packages</h2>
		<p>First run the below three commands one by one to remove all Java related packages from Ubuntu 14.04 like <b>Sun, Oracle, OpenJDK, IcedTea plugins, GIJ</b>:</p>
		<script src="https://gist.github.com/ajgupta/44443aa08c058e4255d8.js"></script>
		<h2>Purge config files</h2>
		<p>After removing all the packages you need to purge all the <b>config files</b> from your Ubuntu system. For that run the following command:</p>
		<script src="https://gist.github.com/ajgupta/2a0438a3088848d9939e.js"></script>
		<h2>Remove cache directory</h2>
		<p>After purging the config files we need to remove Java config and cache directory from you Ubuntu system. Run the following command to remove the cache directory:</p>
		<script src="https://gist.github.com/ajgupta/cca3c7e3b9b89994231e.js"></script>
		<h2>Remove manually installed JVM's</h2>
		<p>If you have installed any other JVM's then this is the time to remove them. Run the following command:</p>
		<script src="https://gist.github.com/ajgupta/c5d36595e0510359e261.js"></script>
		<h2>Remove all leftover Java entries</h2>
		<p>After uninstalling all the java components from your system some java entries might still be left in your Ubuntu system. To get rid of them run the following command:</p>
		<script src="https://gist.github.com/ajgupta/0fb4d48d4d0c1454c784.js"></script>
		<h2>Remove java directories from system</h2>
		<p>This is the final step in removing Java from your system. After uninstalling the java packages the java directories might still be there in your system. To remove them you need to first find if there are any left. Use the following commands to find any leftover directories:</p>
		<script src="https://gist.github.com/ajgupta/784f8e791cc8eb114a89.js"></script>
		<p>If after running the above script you get any output similar to 'jre1.5/bin/pack200' then run the following command (replace jre1.5 with the directory name that you got in the output at the terminal) to remove the leftover java directory:</p>
		<script src="https://gist.github.com/ajgupta/ea7a12462286f4ab2279.js"></script>
	</div>
</div> 
		
		
		
		
		

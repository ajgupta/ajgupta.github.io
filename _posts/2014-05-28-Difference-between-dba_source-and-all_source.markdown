---
layout: post
title: Difference between dba_source and all_source
category: Oracle
tags: pl/sql 
year: 2014
month: 05
day: 28
published: false
image: post_two.png
---

<div class="row">	
	<div class="span9 columns">
		<h2>In short the difference between dba_source and all_source is:</h2>
		<p>ALL_SOURCE describes the text source of the stored objects <b>accessible</b> to the current user whereas DBA_SOURCE is not limited for a particular user describes the text source of <b>all stored objects</b> in the database.</p>
		<h2>Wait that's not all there is!</h2>
		<p>Both dba_source and all_source have 5 columns each: OWNER, NAME,TYPE, LINE and TEXT. Other then these two there is one more view called USER_SOURCE which describes the text source of the stored objects <b>owned by the current user</b>.</p>
		<h2>Just tell me how to use it!</h2>
		<p>Most common way to use these:</p>
		<code>SELECT * FROM dba_source<br>where TEXT like '%package.procedure/function_name%'</code>
		<p>Source: Oracle Docs for <a href="http://docs.oracle.com/cd/B19306_01/server.102/b14237/statviews_4102.htm" target="_blank">DBA_SOURCE</a>, <a href="http://docs.oracle.com/cd/B19306_01/server.102/b14237/statviews_2063.htm" target="_blank">ALL_SOURCE</a>
	</div>
</div> 
		
		
		
		
		

---
layout: post
title: Difference between dba_source and all_source
category: Oracle
tags: pl/sql 
year: 2014
month: 05
day: 28
published: true
description: ALL_SOURCE describes code of the stored objects accessible to current user. DBA_SOURCE also describes text for stored objects but it is not limited to a particular user.

---

<div class="row">	
	<div class="span9 columns">
		<h2>In short the difference between dba_source and all_source is:</h2>
		<p>ALL_SOURCE describes the text source (all the code) of the stored objects <b>accessible</b> to the current user. Whereas DBA_SOURCE is not limited for a particular user, it describes the text source of <b>all stored objects</b> in the database.</p>
		<h2>Wait that's not all there is!</h2>
		<p>Both dba_source and all_source have 5 columns: OWNER, NAME,TYPE, LINE and TEXT. Other then these two there is one more view called USER_SOURCE which describes the text source of the stored objects <b>owned by the current user</b>.</p>
		<h2>Just tell me how to use it!</h2>
		<p>Most common way to use these:</p>
		<script src="https://gist.github.com/ajgupta/90a59925ba66d7a45ba9.js"></script><br>
		<br>
		<p>Source: Oracle Docs for <a href="http://docs.oracle.com/cd/B19306_01/server.102/b14237/statviews_4102.htm" target="_blank">DBA_SOURCE</a>, <a href="http://docs.oracle.com/cd/B19306_01/server.102/b14237/statviews_2063.htm" target="_blank">ALL_SOURCE</a>
	</div>
</div> 
		
		
		
		
		

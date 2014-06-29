---
layout: post
title: Adjust width of Disqus comments
category: Oracle
year: 2014
month: 06
day: 29
published: true
description: By default Disqus covers 100% width of your site. This might cause an issue with rendering of the page depending on design of your site. Learn how I adjusted the width of Disqus comments on my blog. 

---
<div class="row">
	<div class="span9 columns">
		<p>By default Disqus covers up 100% of the width of your blog. If your design is a bit different like mine then this might be a problem as while scrolling Disqus might overlap certain elements  on the page.</p>
		<h2>How to change the width of Disqus comments block?</h2>
		<p>If you will see the Disqus code:</p>
			<script src="https://gist.github.com/anonymous/6fe58e246a077327bf08.js"></script>
		<p>Now this code does not have any width element, so we need to follow the CSS method.</p>
		<h2>The CSS way:</h2>
		<p>Just create a <b>div element</b> with a class as follows:</p>
			<script src="https://gist.github.com/anonymous/77f9a65725a3f354f30b.js"></script>
		<p>After this you need to add properties to this element in your CSS file:</p>
			<script src="https://gist.github.com/anonymous/0122f13394b23a9ecd6e.js"></script>
		<p>To check how much width you need, check that by playing with <a href="https://developer.chrome.com/devtools/index" target="_blank">Google Devtools</a>. I have set mine at 70% width.</p>
		<p>You can checkout <a href="https://help.disqus.com/customer/portal/articles/545277-disqus-appearance-tweaks"target="_blank">this</a> article for more tweaks and customizations with Disqus comments.</p>
	</div>
 </div> 
		
		
		
		
		

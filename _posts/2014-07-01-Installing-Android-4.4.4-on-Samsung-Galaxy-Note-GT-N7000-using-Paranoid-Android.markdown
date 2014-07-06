---
layout: post
title: Installing Android 4.4.4 on Samsung Galaxy Note GT N7000 using Paranoid Android
year: 2014
month: 07
day: 01
published: false
description:  

---
<div class="row">
	<div class="span9 columns">
		<p>I own a Samsung Galaxy Note N7000. Till now I had Cyanogenmod installed on it. But I was getting tired of it as Cyanogenmod is not releasing any <b>stable</b> updates for it. So a week ago I installed Paranoid Android ROM Android 4.4.4. I was really fortunate as the stable version was only released on 25th June 2014.</p>
		<p>First I downloaded the <a href="http://aospal.hostingsharedbox.com/aospal/roms/n7000/" target="blank">Paranoid Android ROM</a>. Then I downloaded Micro module Google Apps package from <a href="http://forum.xda-developers.com/showthread.php?t=2397942" target="blank"</a>XDA Developers</a>. I emptied my SD Card and added both of the above files into it. Then I booted up the Galaxy Note to recovery mode by holding the Volume up + Power + Home buttons together. Then I did a factory reset, wiped cache, wiped Dalvik cache. Then I installed both the files from SD card. Again cleared Dalvik cache and wiped cache partition. And then finally restarted the N7000 to complete the process. </p>
		<p>After the restart it got stuck at the boot animation screen:</p>
		![](/static/images/Paranoid-Android-n7000/Boot-animation-Paranoid-Android.JPG)
		<p>So I used the power button and force restarted the Note and voila! it worked. The phone restarted perfectly and I was able to add my Google account.</p>
		<p>Since then its been a few days since I have been on this ROM. Paranoid Android is mostly stable other than a few hiccups.</p>
		<p>The following is a screen shot of my homescreen. You can notice the semi transparent notification bar at the top. The icons are a bit bigger. Mostly clean UI.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Home-screen-screenshot.png)
		<p>If we go into the Apps showcase you might again notice the icons are a bit bigger.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-All-apps-screenshot.png)
		<p>In the About phone you can see the Android version 4.4.4 and the Paranoid Android version 4.4.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-about-phone-screenshot.png)
		<p>In Paranoid Android if you will go to Settings> Apps> and then click on any app then you will see three options Disable/Uninstall, Force stop and <b>Blacklist</b>. Never tried Blacklisting an app. A word of advice here there are <b>no bloatwares</b> in this ROM, so <b>do not</b> uninstall any system apps like Documents, etc. Learnt this the hard way, uninstalled Documents app using Titanium Backup and now I see its implications. In PA Documents is closely linked to the Download Manager.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-app-info-screenshot.png)
		<p>As you can see in the image below there is not much change in the Task Manager.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-apps-in-background-screenshot.png)
		<p>Awesome thing about this ROM or should I say this Android version is that I can configure App permissions for each app individually. To configure it go to Settings> App Privacy> Select the app and choose the permissions.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-apps-permissions-screenshot.png)
		<p>Nothing has changed in the apps list except that there is a new tab for disabled apps.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-apps-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-disabled-apps-screenshot.png)
		<p>Battery stats are much accurate and I can happily say that battery usage has decreased as well. My battery lasts longer now. Thanks PA devs.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Battery stats-screenshot.png)
		<p>I have always wanted to use Google Launcher but in Cyanogenmod it wasn't compatible (could be because it was Cyanogenmod 10). But in Paranoid Android Google Launcher came preinstalled with the ROM and works just fine. I removed the persistent search bar from top of each homescreen using Xposed Framework as I don't use Google Now or voice search, etc.</p>
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-choose-launcher-screenshot.png)
		
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-dialer-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-display-settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-floating-notifications-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Google-camera-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-google-camera-settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-more-settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Notification-bar-pulldown-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-notifications-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-power button-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-processor-settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-reboot-options-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-running-apps-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-Settings-themes-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-system-settings-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-update-check-screenshot.png)
		![](/static/images/Paranoid-Android-n7000/Paranoid-Android-4.4.4-volume-up-screenshot.png)
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
		
		
		
		
		

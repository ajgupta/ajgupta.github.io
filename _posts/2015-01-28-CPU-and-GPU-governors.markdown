---
layout: post
title: All about CPU Governors and GPU governors
category: Android
tags: Android 
year: 2015
month: 01
day: 28
published: true
description: This post explains in detail everything a user needs to know about CPU and GPU governors and their various types.

---

<div class="row">	
	<div class="span9 columns">
		<p class="MsoNormal">
Applications needed for using these features: <br>
1. <a href="https://play.google.com/store/apps/details?id=com.mhuang.overclocking&hl=en" target="_blank">SetCPU</a><br>
2. <a href="https://play.google.com/store/apps/details?id=it.sineo.android.noFrillsCPU&hl=en" target="_blank">No-frills CPU Control</a><br>
3. Inbuilt Performance Settings (Only in custom roms, Free)<br>
4. <a href="https://play.google.com/store/apps/details?id=com.bigeyes0x0.trickstermod&hl=en" target="_blank">Trickster Mod</a> <br>

<br>
<br>
What is a CPU governor?<br>
<br>
A CPU governor in Android controls how the CPU raises and lowers its frequency in response to the demands the user is placing on their device. Governors are especially important in smartphones and tablets because they have a large impact on the apparent fluidity of the interface and the battery life of the device over a charge. <br>
<br>
NOTE: You cannot change your CPU governor unless your phone is rooted and you have a ROM or app that lets you make a change. Also, different kernels (the intermediary software between your phone's hardware and the operating system) offer different sets of governors. <br>
<br>

Available CPU governors:<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpFirst"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">1.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->OnDemand
Governor:<br>
This governor has a hair trigger for boosting clockspeed to the maximum
speed
set by the user. If the CPU load placed by the user abates, the
OnDemand
governor will slowly step back down through the kernel's frequency
steppings
until it settles at the lowest possible frequency, or the user executes
another
task to demand a ramp.<br>
<br>
OnDemand has excellent interface fluidity because of its high-frequency
bias,
but it can also have a relatively negative effect on battery life
versus other
governors. OnDemand is commonly chosen by smartphone manufacturers
because it
is well-tested, reliable, and virtually guarantees the smoothest
possible
performance for the phone.<br>
<br>
This final fact is important to know before you read about the
Interactive
governor: OnDemand scales its clockspeed in a work queue context. In
other
words, once the task that triggered the clockspeed ramp is finished,
OnDemand
will attempt to move the clockspeed back to minimum. If the user
executes
another task that triggers OnDemand's ramp, the clockspeed will bounce
from
minimum to maximum. This can happen especially frequently if the user
is
multi-tasking. This, too, has negative implications for battery life.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">2.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]--><span
 style="">&nbsp;</span>OndemandX:<br>
Basically an ondemand with suspend/wake profiles. This governor is
supposed to
be a battery friendly ondemand. When screen is off, max frequency is
capped at
500 mhz. Even though ondemand is the default governor in many kernel
and is
considered safe/stable, the support for ondemand/ondemandX depends on
CPU
capability to do fast frequency switching which are very low latency
frequency
transitions. I have read somewhere that the performance of
ondemand/ondemandx
were significantly varying for different i/o schedulers. This is not
true for
most of the other governors.<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"><o:p>&nbsp;</o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">3.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Performance
Governor:<br>
This locks the phone's CPU at maximum frequency. While this may sound
like an
ugly idea, there is growing evidence to suggest that running a phone at
its
maximum frequency at all times will allow a faster race-to-idle.
Race-to-idle
is the process by which a phone completes a given task, such as syncing
email,
and returns the CPU to the extremely efficient low-power state. This
still
requires extensive testing, and a kernel that properly implements a
given CPU's
C-states (low power states).<o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"><o:p>&nbsp;</o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">4.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Powersave
Governor:<br>
The opposite of the Performance governor, the Powersave governor locks
the CPU
frequency at the lowest frequency set by the user.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"><o:p>&nbsp;</o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">5.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Conservative
Governor:<br>
This biases the phone to prefer the lowest possible clockspeed as often
as
possible. In other words, a larger and more persistent load must be
placed on
the CPU before the conservative governor will be prompted to raise the
CPU
clockspeed. Depending on how the developer has implemented this
governor, and
the minimum clockspeed chosen by the user, the conservative governor
can
introduce choppy performance. On the other hand, it can be good for
battery
life.<br>
<br>
The Conservative Governor is also frequently described as a "slow
OnDemand," if that helps to give you a more complete picture of its
functionality.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">6.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Userspace
Governor:<br>
This governor, exceptionally rare for the world of mobile devices,
allows any
program executed by the user to set the CPU's operating frequency. This
governor is more common amongst servers or desktop PCs where an
application
(like a power profile app) needs privileges to set the CPU clockspeed.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">7.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Min
Max<br>
well this governor makes use of only min &amp; maximum frequency
based on
workload... no intermediate frequencies are used.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">8.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->Interactive
Governor:<br>
Much like the OnDemand governor, the Interactive governor dynamically
scales
CPU clockspeed in response to the workload placed on the CPU by the
user. This
is where the similarities end. Interactive is significantly more
responsive
than OnDemand, because it's faster at scaling to maximum frequency.<br>
<br>
Unlike OnDemand, which you'll recall scales clockspeed in the context
of a work
queue, Interactive scales the clockspeed over the course of a timer set
arbitrarily by the kernel developer. In other words, if an application
demands
a ramp to maximum clockspeed (by placing 100% load on the CPU), a user
can
execute another task before the governor starts reducing CPU frequency.
This
can eliminate the frequency bouncing discussed in the OnDemand section.
Because
of this timer, Interactive is also better prepared to utilize
intermediate
clockspeeds that fall between the minimum and maximum CPU frequencies.
This is another
pro-battery life benefit of Interactive.<br>
<br>
However, because Interactive is permitted to spend more time at maximum
frequency than OnDemand (for device performance reasons), the
battery-saving
benefits discussed above are effectively negated. Long story short,
Interactive
offers better performance than OnDemand (some say the best performance
of any
governor) and negligibly different battery life.<br>
<br>
Interactive also makes the assumption that a user turning the screen on
will
shortly be followed by the user interacting with some application on
their
device. Because of this, screen on triggers a ramp to maximum
clockspeed,
followed by the timer behavior described above.<br>
<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">9.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span></span><!--[endif]-->InteractiveX
Governor:<br>
Created by kernel developer "Imoseyon," the InteractiveX governor is
based heavily on the Interactive governor, enhanced with tuned timer
parameters
to better balance battery vs. performance. The InteractiveX governor's
defining
feature, however, is that it locks the CPU frequency to the user's
lowest
defined speed when the screen is off.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">10.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Smartass<br>
Is based on the concept of the interactive governor.<br>
I have always agreed that in theory the way interactive works – by
taking over
the idle loop – is very attractive. I have never managed to tweak it so
it
would behave decently in real life. Smartass is a complete rewrite of
the code
plus more. I think its a success. Performance is on par with the “old”
minmax
and I think smartass is a bit more responsive. Battery life is hard to
quantify
precisely but it does spend much more time at the lower frequencies.<br>
Smartass will also cap the max frequency when sleeping to. Lets take
for
example the 528/176 kernel, it will sleep at 352/176. No need for sleep
profiles any more!"<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">11.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->SmartassV2:<br>
Version 2 of the original smartass governor from Erasmux. The governor
aim for
an "ideal frequency", and ramp up more aggressively towards this freq
and less aggressive after. It uses different ideal frequencies for
screen on
and screen off, namely awake_ideal_freq and sleep_ideal_freq. This
governor
scales down CPU very fast (to hit sleep_ideal_freq soon) while screen
is off
and scales up rapidly to awake_ideal_freq (500 mhz for GS2 by default)
when
screen is on. There's no upper limit for frequency while screen is off
(unlike
Smartass). So the entire frequency range is available for the governor
to use
during screen-on and screen-off state. The motto of this governor is a
balance
between performance and battery.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">12.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Scary<br>
A new governor wrote based on conservative with some smartass features,
it
scales accordingly to conservatives laws. So it will start from the
bottom,
take a load sample, if it's above the upthreshold, ramp up only one
speed at a
time, and ramp down one at a time. It will automatically cap the off
screen
speeds to 245Mhz, and if your min freq is higher than 245mhz, it will
reset the
min to 120mhz while screen is off and restore it upon screen awakening,
and
still scale accordingly to conservatives laws. So it spends most of its
time at
lower frequencies. The goal of this is to get the best battery life
with decent
performance. It will give the same performance as conservative right
now, it
will get tweaked over time.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">13.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Lagfree:<br>
Lagfree is similar to ondemand. Main difference is it's optimization to
become
more battery friendly. Frequency is gracefully decreased and increased,
unlike
ondemand which jumps to 100% too often. Lagfree does not skip any
frequency
step while scaling up or down. Remember that if there's a requirement
for
sudden burst of power, lagfree can not satisfy that since it has to
raise cpu
through each higher frequency step from current. Some users report that
video
playback using lagfree stutters a little.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">14.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Smoothass:<br>
The same as the Smartass “governor” But MUCH more aggressive &amp;
across the
board this one has a better battery life that is about a third better
than
stock KERNEL<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">15.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Brazilianwax:<br>
Similar to smartassV2. More aggressive ramping, so more performance,
less
battery<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">16.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->SavagedZen:<br>
Another smartassV2 based governor. Achieves good balance between
performance
&amp; battery as compared to brazilianwax.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">17.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Lazy:<br>
This governor from Ezekeel is basically an ondemand with an additional
parameter min_time_state to specify the minimum time CPU stays on a
frequency
before scaling up/down. The Idea here is to eliminate any instabilities
caused
by fast frequency switching by ondemand. Lazy governor polls more often
than
ondemand, but changes frequency only after completing min_time_state on
a step
overriding sampling interval. Lazy also has a screenoff_maxfreq
parameter which
when enabled will cause the governor to always select the maximum
frequency
while the screen is off.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">18.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Lionheart:<br>
Lionheart is a conservative-based governor which is based on samsung's
update3
source.<br>
The tunables (such as the thresholds and sampling rate) were changed so
the
governor behaves more like the performance one, at the cost of battery
as the
scaling is very aggressive.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">19.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->LionheartX<br>
LionheartX is based on Lionheart but has a few changes on the tunables
and
features a suspend profile based on Smartass governor.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">20.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Intellidemand:<br>
Intellidemand aka Intelligent Ondemand from Faux is yet another
governor that's
based on ondemand. Unlike what some users believe, this governor is not
the
replacement for OC Daemon (Having different governors for sleep and
awake). The
original intellidemand behaves differently according to GPU usage. When
GPU is
really busy (gaming, maps, benchmarking, etc) intellidemand behaves
like
ondemand. When GPU is 'idling' (or moderately busy), intellidemand
limits max
frequency to a step depending on frequencies available in your
device/kernel
for saving battery. This is called browsing mode. We can see some
'traces' of
interactive governor here. Frequency scale-up decision is made based on
idling
time of CPU. Lower idling time (&lt;20%) causes CPU to scale-up
from current
frequency. Frequency scale-down happens at steps=5% of max frequency.
(This
parameter is tunable only in conservative, among the popular governors)<br>
To sum up, this is an intelligent ondemand that enters browsing mode to
limit
max frequency when GPU is idling, and (exits browsing mode) behaves
like
ondemand when GPU is busy; to deliver performance for gaming and such.
Intellidemand does not jump to highest frequency when screen is off.<br>
<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">21.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Hotplug
Governor:<br>
The Hotplug governor performs very similarly to the OnDemand governor,
with the
added benefit of being more precise about how it steps down through the
kernel's frequency table as the governor measures the user's CPU load.
However,
the Hotplug governor's defining feature is its ability to turn unused
CPU cores
off during periods of low CPU utilization. This is known as
"hotplugging."<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">22.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->BadAss
Goveronor:<br>
Badass removes all of this "fast peaking" to the max frequency. To
trigger a frequency increase, the system must run a bit with high load,
then
the frequency is bumped. If that is still not enough the governor gives
you
full throttle. (this transition should not take longer than 1-2
seconds,
depending on the load your system is experiencing)<br>
Badass will also take the gpu load into consideration. If the gpu is
moderately
busy it will bypass the above check and clock the cpu with 1188Mhz. If
the gpu
is crushed under load, badass will lift the restrictions to the cpu.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">23.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Wheatley:<br>
Building on the classic 'ondemand' governor is implemented Wheatley
governor.
The governor has two additional parameters. Wheatley works as planned
and does
not hinder the proper C4 usage for task where the C4 can be used
properly. So
the results show that Wheatley works as intended and ensures that the
C4 state
is used whenever the task allows a proper efficient usage of the C4
state. For
more demanding tasks which cause a large number of wakeups and prevent
the
efficient usage of the C4 state, the governor resorts to the next best
power
saving mechanism and scales down the frequency. So with the new
highly-flexible
Wheatley governor one can have the best of both worlds.<br>
<br>
Obviously, this governor is only available on multi-core devices.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">24.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Lulzactive:<br>
It's based on Interactive &amp; Smartass governors.<br>
Old Version: When workload is greater than or equal to 60%, the
governor scales
up CPU to next higher step. When workload is less than 60%, governor
scales
down CPU to next lower step. When screen is off, frequency is locked to
global
scaling minimum frequency.<br>
New Version: Three more user configurable parameters: inc_cpu_load,
pump_up_step, pump_down_step. Unlike older version, this one gives more
control
for the user. We can set the threshold at which governor decides to
scale
up/down. We can also set number of frequency steps to be skipped while
polling
up and down.<br>
When workload greater than or equal to inc_cpu_load, governor scales
CPU
pump_up_step steps up. When workload is less than inc_cpu_load,
governor scales
CPU down pump_down_step steps down.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">25.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Pegasusq/Pegasusd<br>
<br>
The Pegasus-q / d is a multi-core based on the Ondemand governor and
governor
with integrated hot-plugging. It is quite stable and has the same
battery life
as ondemand. However, it is less stable than HYPER on some devices like
the S2
(before the PegasusQ governor was updated).<br>
Ongoing processes in the queue, we know that multiple processes can run
simultaneously on. These processes are active in an array, which is a
field
called "Run Queue" queue that is ongoing, with their priority values
​​arranged (priority will be used by the task scheduler, which then
decides
which process to run next).<br>
<br>
To ensure that each process has its fair share of resources, each
running for a
certain period and will eventually stop and then again placed in the
queue
until it is your turn again. If a program is terminated, so that others
can run
the program with the highest priority in the current queue is executed.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">26.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Hotplugx<br>
<br>
It's a modified version of Hotplug and optimized for the suspension in
off-screen<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">27.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->AbyssPlug<br>
<br>
It's a Governor derived from hotplug, it works the same way, but with
the
changes in savings for a better battery.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">28.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->MSM
DCVS<br>
<br>
A very efficient and wide range of Dynamic Clock and Voltage Scaling
(DCVS)
which addresses usage models from active standby to mid and high level
processing requirements. It makes the phone's CPU smoothly scale from
low
power, from low leakage mode to blazingly fast performance.Only to be
used by
Qualcomm CPUs.<br>
<br>
MSM is the prefix for the SOC (MSM8960) and DCVS is Dynamic Clock and
Voltage
Scaling. Makes sense, MSM-DCVS<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">29.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->IntelliActive<br>
<br>
Based off Google's Interactive governor with the following enhancements:<br>
<br>
1. self-boost capability from input drivers (no need for PowerHAL
assist)<br>
2. two phase scheduling (idle/busy phases to prevent from jumping
directly to
max freq<br>
3. Checks for offline cpus and short circuits some unnecessary checks
to
improve code execution paths. Therefore, it avoids CPU hotplugging. <br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">30.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Adaptive<br>
<br>
This driver adds a dynamic cpufreq policy governor designed for
latency-sensitive workloads and also for demanding performance.<br>
This governor attempts to reduce the latency of clock so that the
system is
more responsive to interactive workloads in lowest steady-state but to
reduce
power consumption in middle operation level, level up will be done in
step by
step to prohibit system from going to<br>
max operation level.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">31.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Nightmare
<br>
<br>
A PegasusQ modified, less aggressive and more stable. A good compromise
between
performance and battery. In addition to the SoD is a prevention because
it
usually does not hotplug.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">32.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->ZZmove<br>
<br>
The ZZmove Governor by ZaneZam is optimized for low power consumption
when the
screen off, with particular attention to the limitation of consumption
applications in the background with the screen off, such as listening
to music.
ZZmoove is not a good gaming governor as it aims to save battery. This
governor
is still a WIP as the developer is constantly giving updates! Here are
the available
profiles:<br>
<br>
for Default (set governor defaults)<br>
for Yank Battery -&gt; old untouched setting (a very good
battery/performance
balanced setting DEV-NOTE: highly recommended!)<br>
for Yank Battery Extreme -&gt; old untouched setting (like yank
battery but
focus on battery saving)<br>
for ZaneZam Battery -&gt; old untouched setting (a more 'harsh'
setting
strictly focused on battery saving DEV-NOTE: might give some lags!)<br>
for ZaneZam Battery Plus -&gt; NEW! reworked 'faster' battery
setting
(DEV-NOTE: recommended too!&nbsp; )<br>
for ZaneZam Optimized -&gt; old untouched setting (balanced setting
with no
focus in any direction DEV-NOTE: relict from back in the days, even
though some
people still like it!)<br>
for ZaneZam Moderate -&gt; NEW! setting based on 'zzopt' which has
mainly (but
not strictly only!) 2 cores online<br>
for ZaneZam Performance -&gt; old untouched setting (all you can
get from
zzmoove in terms of performance but still has the fast down
scaling/hotplugging
behaving)<br>
for ZaneZam InZane -&gt; NEW! based on performance with new auto
fast scaling
active. a new experience!<br>
for ZaneZam Gaming -&gt; NEW! based on performance with new scaling
block
enabled to avoid cpu overheating during gameplay<br>
(since version 0.9 beta4: cpu temperature threshold of 65°C enabled if
exynos4
cpu temperature reading support was compiled with the governor)<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">33.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Sleepy<br>
<br>
The Sleepy (formerly known as Solo) is an attempt to strike a balance
between
performance and battery power to create. It is based on Ondemand. It
includes
some tweaks like the Down_sampling variable and other features that set
by the
user through the sysfs of "echo" call. Sleepy is quite similar to
Ondemandx.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">34.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Hyper<br>
<br>
The Hyper (formerly known as kenobi) is an aggressive smart and
smooth,based on
the Ondemand and is equipped with several features of Ondemandx suspend
profiles. (Added by sysfs, the settings suspend_freq and suspend
Imoseyon's
code) is the behavior of the HYPER. It also has the fast_start
deep_sleep
variable and detection features. In addition, the maximum frequency is
in
suspend mode 500Mhz.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">35.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->SmartassH3<br>
<br>
The SmartassH3 governor is designed for battery saving and not pushing
the
phones performance, since doing that drains battery and that's the one
thing
people keep asking for more of. Based on SmartassV2. <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">36.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->SLP <br>
<br>
It is a mix of pegasusq and ondemand. Therefore, it has a balance
between
battery savings and performance. <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">37.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->NeoX <br>
<br>
An optimized version of the pegasusq governor but with some extra
tweaks for
better performance. This means more battery drainage than the original
PegasusQ.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">38.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->ZZmanx<br>
<br>
ZZmanx is exactly the same as ZZmove, but it has been renamed because
DorimanX
made it into his own version (possibly better performance) . However,
it still
suffers from below average gaming performance. (Refer to ZZmoove
description for
guide on profiles)<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">39.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->OnDemandPlus
<br>
A governor based off of OnDemand and Interactive. It provides a balance
between
performance, and saving battery.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">40.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->DynInteractive
<br>
A dynamic interactive Governor. This Governor dynamically adapts it's
own CPU
frequencies within your parameters based off the system(s) load.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">41.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Smartmax<br>
<br>
This is a new governor which is a mix between ondemand and smartassv2.
By
default this is configured for battery saving,so this is NOT a gamer
governor!
This is still WIP!<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">42.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Ktoonservative\KtoonservativeQ<br>
<br>
A combination of ondemand and conservative. Ktoonservative contains a
hotplugging variable which determines when the second core comes
online. The
governor shuts the core off when it returns to the second lowest
frequency thus
giving us a handle on the second performance factor in our CPUs
behavior. <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">43.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Performance
may cry (PMC)<br>
A governor based on Smartmax except it's heavily tweaked for better and
maximum
battery life. This is not a gaming governor!<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">44.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Dance
Dance<br>
Based on conservative with some smartass features, it scales
accordingly to
conservatives laws. So it will start from the bottom, take a load
sample, if
it's above the upthreshold, ramp up only one speed at a time, and ramp
down one
at a time. It will automatically cap the off screen speeds to 245Mhz,
and if
your min freq is higher than 245mhz, it will reset the min to 120mhz
while
screen is off and restore it upon screen awakening, and still scale
accordingly
to conservatives laws. So it spends most of its time at lower
frequencies. The
goal of this is to get the best battery life with decent performance.
It will
give the same performance as conservative right now, it will get
tweaked over
time.&nbsp; <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">45.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->AbyssPlugv2<br>
AbyssPlugv2 is a rewrite of the original CPU governor. It also fixes
the
problem where the governor is set only for the first core, but now
governs all
cores right from whatever utility you use. There have been comments on
the lack
of stability with this governor.&nbsp; <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">46.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->IntelliMM<br>
A rewrite of the old Min Max governor and has 3 cpu states: Idle, UI
and Max.
Pretty much a smarter Min Max governor.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">47.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Interactive
Pro<br>
A newer (modified) version of interactive which is optimized for
devices such
as the One Plus One. It is a more efficient than the original
Interactive
because it continuously re-evaluates the load of each CPU therefore
allowing
the CPU to scale efficiently.<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">48.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Slim<br>
A new governor from the cm branch and the slimrom project. A
performance
optimized governor. Found on newer devices only such as the One Plus
One. This
CPU governor will fall back to be the performance governor if very high
load is
detected<br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">49.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Ondemand
EPS<br>
Once again, a modified version of Ondemand and is optimized for newer
devices.
It is based on the Semaphore Kernel's Ondemand which is more optimized
for
battery life and better performance than the traditional ondemand
governor.&nbsp; <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">50.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Smartmax
EPS<br>
A newer smartmax governor that has been slightly optimized for newer
devices. <br style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpMiddle"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">51.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Uberdemand<br>
Uberdemand is Ondemand with 2-phase feature meaning it has a soft cap
at 1728
MHz so your cpu won't always go directly to max, made by Chet Kener.<br
 style="">
<!--[if !supportLineBreakNewLine]--><br style="">
<!--[endif]--><o:p></o:p></p>
<p class="MsoListParagraphCxSpLast"
 style="text-indent: -0.25in;"><!--[if !supportLists]--><span
 style=""><span style="">52.<span
 style="font-family: &quot;Times New Roman&quot;; font-style: normal; font-variant: normal; font-weight: normal; font-size: 7pt; line-height: normal; font-size-adjust: none; font-stretch: normal;">&nbsp;&nbsp;
</span></span></span><!--[endif]-->Yankactive<br>
A slightly modified interactive based governor by Yank555.lu. Possibly
better
performance or battery life.<br>
<br>
Hotplugging drivers:<br>
- mpdecision (Qualcomm's default hotplugging driver)<br>
- intelliplug (Great for performance, more customization options)<br>
- Alucard HotPlug (A great hotplugging driver by Alucard)<br>
Custom kernels may have their own hotplugging drivers but they are
usually based
on these ones. <br>
<br>
I recommend staying with the default hotplugging driver or keeping the
setting
on AUTO. If you want to experiment, be sure to expect better/worse
battery
life!<br>
<br>
<br>
GPU governors<br>
<br>
Simple: It's a new governor for the gpu frequency scaling. It will
allow a more
fine grained control over how the gpu scales up and down then the
previous
ones. This means either more performance or more battery savings <br>
<br>
Ondemand: Much like the CPU governor, Ondemand will ramp up the
frequency when
a load is detected. A good balance between performance and battery
savings. <br>
<br>
MSM-Adreno: The default GPU governor used by qualcomm for their adreno
GPUs. It
is more performance orientated than ondemand therefore it gives better
performance in games but less battery life. <br>
<br>
Performance: As the name suggests, this keeps your GPU running at the
max
frequency. This is a governor if you want the best possible experience
in games
but you don't care about your battery life. <br>
<br>
Powersave: Like the CPU governor, this keeps your GPU running at the
lowest
possible frequency. Best battery life, extreme lag in games. <br>
<br>
<br>
<br>
Categorization:<br>
<br>
There are four different categories CPU governors can exist as.<br>
<br>
1) Ondemand Based:<br>
Works on "ramp-up on high load" principle. CPU busy-time is taken
into consideration for scaling decisions. Members: Ondemand, OndemandX,
Intellidemand, Lazy, Lagfree, PegasusQ, HYPER, Wheatley, Hotplug,
HotplugX,
AbyssPlug, AbyssPlugv2, Nightmare, Sleepy.<br>
2) Conservative Based:<br>
Works by biasing the phone to prefer the lowest possible clockspeed as
often as
possible. Members: Conservative, Lionheart, LionheartX<br>
<br>
3) Interactive Based:<br>
Works on "make scaling decision when CPU comes out of idle-loop"
principle. Members: Interactive, InteractiveX, Intelliactive,
Lulzactive, Luzactiveq,
Smartass, SmartassV2, SmartassH3, Brazilianwax, SavagedZen,
Dyninteractive.<br>
<br>
4) Unique Category:<br>
These do not fall into any other category above and/or possess unique
attributes. Members: Userspace, Powersave, Performance, Min Max,
ZZmove, MSM DCVS<br>
<br>
5) Hybrid Category:<br>
These have a mix of two (or more) CPU governor behaviors. Members:
Smartmax,
Dancedance, Performance May Cry(PMC), Ktoonservative, KtoonservativeQ<br>
<br>
<br>
Here are some CPU Governors I recommend...<br>
<br>
<br>
Rating system:<br>
Best - This CPU governor is simply the best (for the category), highly
recommended.<br>
Great - This CPU governor is very good, will suit most people.<br>
Good - This CPU governor is good, but might not suit everyone.<br>
Requires tuning - This CPU governor requires tuning, not for beginners.<br>
<br>
If your kernel (not the rom) doesn't have the CPU governors that has
been
marked as 'best', use the ones that have been marked as 'great'. <br>
<br>
<br>
Also, if there is more than one governor marked as 'best', choose the
one that
is available for you. If all are available, choose any. <br>
<br>
<br>
For performance:<br>
<br>
<br>
Single-core:<br>
- Performance - Best<br>
- Min Max - Great<br>
<br>
Multi-core:<br>
- Performance - Best<br>
- Min Max - Great<br>
<br>
<br>
For battery life:<br>
<br>
Single-core:<br>
- Conservative - Best<br>
- Powersave - Good<br>
<br>
Multi-core:<br>
- Conservative - Best<br>
- SLP/Sleepy - Great<br>
- Perfomance may cry (PMC) - Best<br>
- Powersave - Good<br>
- Ktoonservative(Q) - Great<br>
- Smartmax - Best<br>
<br>
<br>
<br>
For balanced battery saving and performance:<br>
<br>
<br>
Single-core:<br>
- Interactive/Intelliactive - Best<br>
- Ondemand/OndemandX - Stock, Best<br>
- SmartassV2 - Great<br>
<br>
Multi-core:<br>
- MSM DCSV - Great, not common<br>
- LulzactiveQ - Requires tuning<br>
- Intelliactive- Great<br>
- Interactive(X) - Great<br>
- Ondemand/OndemandX - Stock, Best<br>
- Pegasus(q/d) - Best<br>
- SmartassV2 - Great <br>
- Wheatley - Good<br>
- Hotplug/HotplugX - Good <br>
- HYPER - Best <br>
- ZZMove - Requires tuning<br>
- Dancedance - Great<br>
<br>
<br>
For gaming:<br>
<br>
Single-core:&nbsp; <br>
- Interactive(X) - Best<br>
- Performance - Great<br>
- Ondemand/OndemandX - Great<br>
- SmartassV2 - Best<br>
<br>
Multi-core:<br>
- Lionheart/LionheartX - Best<br>
- Dancedance - Good<br>
- Intelliactive - Great<br>
- SmartassV2 - Great<br>
- Pegasus(Q/D) - Best<br>
- Ondemand/OndemandX - Great<br>
- Hyper - Best<br>
- Performance - Great<br>
- LulzactiveQ - Best<br>
- Intellidemand - Good<br>
<br>
Other CPU Governors not mentioned in the recommended section are either
not
used by people anymore or they are not suited for most people or have
been
removed from kernels.<o:p></o:p></p>

More info/Source/Credits:<br>
<a href="http://forum.xda-developers.com/galaxy-s2/general/ref-kernel-governors-modules-o-t1369817" target="_blank">XDA Forums</a><br>
<a href="http://xda-university.com/as-a-developer/adding-features-to-your-kernel" target="_blank">XDA University</a><br>

	</div>
</div> 
		
		
		
		
		

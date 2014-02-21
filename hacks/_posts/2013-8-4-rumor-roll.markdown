---
layout: hacks
title: Rumor Roll!
subtitle: World's first rumor search engine!
category: hacks
zip_url: https://github.com/ranveeraggarwal/Rumor-Roll/archive/master.zip
issue_url: https://github.com/ranveeraggarwal/Rumor-Roll/issues
repository_url: https://github.com/ranveeraggarwal/Rumor-Roll
codeveloper: Nishant Kumar Singh, Adit Kabra and Bhargav Chippada
---

World's first rumor search engine, this hack makes the use of Yahoo! Boss API to search for rumors about the given search query. Type in the name of your favourite superstar or a company that you follow, and we'll filter out the pages, tweets and youtube videos related to the rumors reagarding that particular entity.

The following APIs were used:

* Yahoo! Boss
* Twitter API
* Youtube API
* Twitter Bootstrap v3.0

Here are a few snapshots:

<script>
$(document).ready(function() {
    $('.pics').cycle({
		fx: 'scrollDown',
		speed:    250, 
                timeout:  2000 
	});
});
</script>

<div class="pics"> 
    <img src="{{site.url}}/img/rr1.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr2.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr3.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr4.jpg" width="400" height="224" /> 
    <img src="{{site.url}}/img/rr5.jpg" width="400" height="224" /> 
</div> 

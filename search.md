---
layout: page
title: Search
---
<form action="get" id="site_search">
<center>
  <input style="font-size:20px;" type="text" id="search_box">&nbsp;
  <input style="font-size:20px;" type="submit" value="search">
</center>
</form>
<br/>&nbsp;
<br/>&nbsp;

<ul id="search_results"></ul>

<script src="{{ site.baseurl }}/js/lunr.js"></script>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
<script src="{{ site.baseurl }}/js/search.js"></script>
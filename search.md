---
layout: page
title: Search
hide: true
permalink: /search/
---
<form action="get" id="site_search" role="search">
<center>
  <input style="font-size:20px;" type="text" id="search_box" autofocus>&nbsp;
  <input style="font-size:20px;" type="submit" value="search">
</center>
</form>
<br/>&nbsp;
<br/>&nbsp;

<ul id="search_results"></ul>

<script src="{{ site.baseurl }}/js/lunr.js"></script>
<script src="https://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
<script src="{{ site.baseurl }}/js/search.js"></script>
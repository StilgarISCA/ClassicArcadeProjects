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
<script src="https://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
<script src="{{ site.baseurl }}/js/search.js"></script>
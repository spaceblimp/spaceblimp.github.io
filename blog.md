---
layout: page
title: Blog
---
<div class="posts">
	<ul>
	{% for post in site.posts %}
	<div class="post">
		<li><span>{{ post.date | date_to_string }}</span> » <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
	</div>
	{% endfor %}
	</ul>
</div>
<div class="pagination">
	{% if paginator.next_page %}
		<a class="pagination-item older" href="{{ site.baseurl }}/page{{paginator.next_page}}">Older</a>
	{% else %}
		<span class="pagination-item older">Older</span>
	{% endif %}
	{% if paginator.previous_page %}
		{% if paginator.page == 2 %}
		<a class="pagination-item newer" href="{{ site.baseurl }}/">Newer</a>
		{% else %}
		<a class="pagination-item newer" href="{{ site.baseurl }}/page{{paginator.previous_page}}">Newer</a>
		{% endif %}
	{% else %}
		<span class="pagination-item newer">Newer</span>
	{% endif %}
</div>

# Allen Academic UIL's Blog

Welcome to Allen UIL's Blog, brought to you by Eric Yang and Warith Rahman :D

The main website can be found [here](https://allen-uil.github.io/).

Both this blog and the main site are managed unofficially by students and not by Allen ISD.
{% assign posts = site.posts %}
{%- if posts.size > 0 -%}
	{%- if page.list_title -%}
	<h2>{{ page.list_title }}</h2>
	{%- endif -%}
	{%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
	{%- for post in posts -%}
	<h3>
		<a href="{{ post.url | relative_url }}">
			{{ post.title | escape }} [{{ post.date | date: date_format }}]
	</a>
	</h3>
	{%- if site.show_excerpts -%}
		{{ post.excerpt }}
	{%- endif -%}
	{%- endfor -%}
{%- endif -%}

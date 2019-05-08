---
layout: default
title: Speakers
---

<div class="row">
  <div id="myArticle" class="col-sm-9">
    <div class="post-area post">
      <article>
        <h1>Speakers</h1>
			<ul>
			  {% for author in site.data.authors %}
			    <li> <b>{{ author[1].name }}</b>, {{ author[1].position }}@{{ author[1].affilation}}
			      <ul>
					  {% assign filtered_posts = site.posts | where: 'author', author[1].short_name %}
					  {% for post in filtered_posts %}
					    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
					  {% endfor %}
				</ul></li><br>
			  {% endfor %}
			</ul>
      </article>
    </div>
  </div>
</div>

<!-- {% for post in filtered_posts %}
					    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
					  {% endfor %} -->
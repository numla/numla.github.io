---
layout: page
---
{% assign n_authors = site.data.authors | size %}
{% assign i_author = 0 %}

{%- for author in site.data.authors -%}
{%- assign i_author = i_author| plus:1 -%}
<div class="person-row">
  <div id="{{author[1].short_name}}" class="person-profile">

  <img src="{{ author[1].picture }}" class="author-avatar u-photo" alt="{{ author[1].name }}">
    
  <div class="author-info">
    <div class="author-name">
      <span class="p-name"><a href="{{site.url}}/people/#{{author[1].short_name}}">{{ author[1].name }}</a>
      <hr style=" border: 0; height: 0; border-top: 1px solid rgba(0, 0, 0, 0.1); border-bottom: 1px solid rgba(255, 255, 255, 0.3);"></span>
      <span>{{author[1].position}}<br></span>
      <span>{{author[1].affilation}}</span>
    </div>
  </div>

  {%- if author[1].links -%}
  <ul class="author-links">
    {%- for link in author[1].links -%}
      {%- if link.url contains "://" -%}
        {%- assign url = link.url -%}
      {%- else -%}
        {%- assign url = link.url | relative_url -%}
      {%- endif -%}
      <li class="author-link">
        <a class="u-url" rel="me" href="{{ url }}"><i class="{{ link.icon | default : 'fas fa-link' }} fa-lg" title="{{ link.title }}"></i></a>
      </li>
    {%- endfor -%}
  </ul>
  {%- endif -%}

  </div>
  <div class="person-list">
    {% assign filtered_posts = site.posts | where: 'author', author[1].short_name %}
    {% if filtered_posts.size > 0 %}
    <h3>Talks</h3>
    {% for post in filtered_posts %}
    <p><a href="{{ post.url }}">{{ post.title }}</a></p>
    {% endfor %}
    {% endif %}
    {%- assign has_publication = false -%}
    {% for publication in site.publications %}
    {% if publication.authors contains author[1].short_name%}
    {% if has_publication %}
    <p><a href="{{ publication.url }}">{{ publication.title }}</a></p>
    {% else %}
    <h3>Publications</h3>
    <p><a href="{{ publication.url }}">{{ publication.title }}</a></p>
    {%- assign has_publication = true -%}
    {% endif %}
    {% endif %}
    {% endfor %}
  </div>
</div>

{%- if i_author < n_authors -%}
<hr style=" border: 0; height: 0; border-top: 1px solid rgba(0, 0, 0, 0.1); border-bottom: 1px solid rgba(255, 255, 255, 0.3);">
{%- endif -%}
{%- endfor -%}

<!-- 
style="align-items: center;
    justify-items: center;" -->
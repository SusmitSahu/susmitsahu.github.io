---
layout: page
permalink: /blog/
title: blog
nav: true
nav_order: 6
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 5
  sort_field: date
  sort_reverse: true
  trail:
    before: 1
    after: 3
---

<div class="post">

{% assign blog_name_size = site.blog_name | size %}
{% assign blog_description_size = site.blog_description | size %}

{% if blog_name_size > 0 or blog_description_size > 0 %}
  <div class="header-bar">
    <h1>{{ site.blog_name }}</h1>
    <h2>{{ site.blog_description }}</h2>
  </div>
{% endif %}

{% assign featured_tags = site.tags | sort %}
{% if featured_tags.size > 0 %}
  <div class="tag-category-list">
    <ul class="p-0 m-0">
      {% for tag in featured_tags %}
        <li>
          <i class="fa-solid fa-hashtag fa-sm"></i>
          <a href="{{ tag | first | slugify | prepend: '/blog/tag/' | prepend: site.baseurl }}">
            {{ tag | first }}
          </a>
        </li>
        {% unless forloop.last %}
          <li>
            <div class="divider">|</div>
          </li>
        {% endunless %}
      {% endfor %}
    </ul>
  </div>
{% endif %}

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
<ul class="post-list">
  {% for post in sorted_posts %}
    {% if post.external_source == blank %}
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% else %}
      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
    {% endif %}
    {% assign year = post.date | date: "%Y" %}
    {% assign tags = post.tags | join: "" %}
    {% assign categories = post.categories | join: "" %}
    {% if tags != "" %}
      {% assign tags_link = tags | slugify | prepend: "/blog/tag/" | append: "/" %}
    {% else %}
      {% assign tags_link = "" %}
    {% endif %}
    <li>
      {% if post.thumbnail %}
        <div class="row">
          <div class="col-sm-9">
      {% endif %}
      <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        {% elsif post.redirect contains '://' %}
          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>
          <svg width="2rem" height="2rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        {% else %}
          <a class="post-title" href="{{ post.redirect | prepend: site.baseurl }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: '%B %-d, %Y' }}
        {% if post.external_source %}
          &nbsp; &middot; &nbsp; {{ post.external_source }}
        {% endif %}
      </p>
      <p class="post-tags">
        <a href="{{ year | prepend: '/blog/' | prepend: site.baseurl }}">
          <i class="fa-solid fa-calendar fa-sm"></i> {{ year }} </a>
        {% if tags != "" %}
          &nbsp; &middot; &nbsp;
          {% for tag in post.tags %}
            <a href="{{ tag | slugify | prepend: '/blog/tag/' | prepend: site.baseurl }}">
              <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>
          {% endfor %}
        {% endif %}
        {% if categories != "" %}
          &nbsp; &middot; &nbsp;
          {% for category in post.categories %}
            <a href="{{ category | slugify | prepend: '/blog/category/' | prepend: site.baseurl }}">
              <i class="fa-solid fa-tag fa-sm"></i> {{ category }}</a>
          {% endfor %}
        {% endif %}
      </p>
    </li>
  {% endfor %}
</ul>

</div>

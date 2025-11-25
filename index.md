---
layout: default
title: Home
---

<header class="blog-header">
    <h1 class="blog-title">{{ site.title }}</h1>
    <p class="blog-description">{{ site.description }}</p>
</header>


<div class="posts-list">
    {% for post in site.posts %}
    {% if post.title == 'Welcome!' %}
    <article class="post-preview card" style="margin-bottom: 2rem; padding: 2rem;">
        <h2 style="margin-bottom: 0.5rem;"><a href="{{ post.url }}" style="color: var(--text-color); text-decoration: none;">{{ post.title }}</a></h2>
        <div class="post-meta" style="color: var(--secondary-text); font-size: 0.9rem; margin-bottom: 1rem;">
            <span>{{ post.date | date: "%B %d, %Y" }}</span> • 
            <span>{{ post.content | number_of_words | divided_by: 200 | plus: 1 }} min read</span>
        </div>
        <p style="margin-bottom: 1rem;">{{ post.excerpt | strip_html | truncate: 200 }}</p>
        <a href="{{ post.url }}" class="back-link">Read More</a>
    </article>
    {% endif %}
    {% endfor %}
</div>
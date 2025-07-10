---
layout: default
title: {% if site.blog_as_home %}Blog{% else %}Home{% endif %}
nav_order: 1
---

{% if site.blog_as_home %}
# Blog

Welcome to our blog! Here you'll find the latest posts and updates.

<div class="blog-posts">
  {% for post in site.posts %}
    <article class="blog-post">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.author %} • by {{ post.author }}{% endif %}
      </div>
      <div class="post-excerpt">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
      <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
    </article>
  {% endfor %}
</div>

{% if site.posts.size == 0 %}
<div class="no-posts">
  <p>No blog posts yet. Check back soon!</p>
</div>
{% endif %}

{% else %}
# Welcome to GitHub Pages Demo

This is a demonstration of GitHub Pages with Jekyll, featuring:

- **Automatic Navigation**: The navigation menu is automatically generated from all pages in the site
- **Responsive Design**: The theme adapts to different screen sizes
- **Clean Layout**: Professional-looking design with gradient headers and card-style content
- **Easy to Extend**: Simply add new `.md` files with front matter to add new pages

## How It Works

The navigation system works by:
1. Scanning all pages in the site
2. Including pages that have a `title` in their front matter
3. Sorting them by `nav_order` (if specified)
4. Automatically generating the navigation menu

## Getting Started

To add a new page:
1. Create a new `.md` file
2. Add front matter with `layout: default` and `title: Your Page Title`
3. Optionally add `nav_order: number` to control menu order
4. Write your content in Markdown

The page will automatically appear in the navigation menu!

## Recent Blog Posts

<div class="recent-posts">
  {% for post in site.posts limit:3 %}
    <article class="recent-post">
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <div class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        {% if post.author %} • by {{ post.author }}{% endif %}
      </div>
      <p>{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
      <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
    </article>
  {% endfor %}
</div>

{% if site.posts.size > 3 %}
<div class="view-all-posts">
  <a href="{{ '/blog/' | relative_url }}" class="view-all">View All Posts →</a>
</div>
{% endif %}
{% endif %}

---

*Last updated: July 10, 2024 at 3:30 PM*

<style>
.recent-posts {
  margin-top: 2rem;
  display: grid;
  gap: 1.5rem;
}

.recent-post {
  border: 1px solid #e1e5e9;
  border-radius: 8px;
  padding: 1.5rem;
  background: #f8f9fa;
}

.recent-post h3 {
  margin-bottom: 0.5rem;
}

.recent-post h3 a {
  text-decoration: none;
  color: #2c3e50;
}

.recent-post h3 a:hover {
  color: #667eea;
}

.recent-post .post-meta {
  color: #666;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.recent-post p {
  margin-bottom: 1rem;
  line-height: 1.6;
}

.read-more {
  color: #667eea;
  font-weight: 500;
  text-decoration: none;
}

.read-more:hover {
  text-decoration: underline;
}

.view-all-posts {
  text-align: center;
  margin-top: 2rem;
}

.view-all {
  background: #667eea;
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 5px;
  text-decoration: none;
  font-weight: 500;
}

.view-all:hover {
  background: #5a67d8;
  text-decoration: none;
}
</style>
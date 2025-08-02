---
layout: page
title: 
subtitle: 
---

<div class="posts-list">
  {% for post in site.posts %}
    <article class="post-preview">
      <div class="post-meta">
        <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
        {% if post.author %}
          <span class="post-author">by {{ post.author }}</span>
        {% endif %}
      </div>
      
      <h2 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      
      {% if post.subtitle %}
        <h3 class="post-subtitle">{{ post.subtitle }}</h3>
      {% endif %}
      
      {% if post.cover-img %}
        <div class="post-image">
          <img src="{{ post.cover-img | relative_url }}" alt="{{ post.title }}" style="max-width: 100%; height: auto; border-radius: 8px; margin: 10px 0;">
        </div>
      {% endif %}
      
      <div class="post-excerpt">
        {{ post.excerpt | default: post.content | strip_html | truncatewords: 50 }}
      </div>
      
      {% if post.tags %}
        <div class="post-tags">
          {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
      
      <a href="{{ post.url | relative_url }}" class="read-more">Read More →</a>
      
      <hr style="margin: 30px 0; border: none; border-top: 1px solid #eee;">
    </article>
  {% endfor %}
</div>

<style>
.posts-list {
  margin: 20px 0;
}

.post-preview {
  margin-bottom: 40px;
}

.post-meta {
  color: #666;
  font-size: 14px;
  margin-bottom: 10px;
}

.post-author {
  margin-left: 10px;
}

.post-title {
  margin: 10px 0;
}

.post-title a {
  color: #333;
  text-decoration: none;
}

.post-title a:hover {
  color: #007bff;
}

.post-subtitle {
  color: #666;
  font-size: 18px;
  margin: 10px 0;
  font-weight: normal;
}

.post-excerpt {
  color: #555;
  line-height: 1.6;
  margin: 15px 0;
}

.post-tags {
  margin: 15px 0;
}

.tag {
  background: #f0f0f0;
  color: #666;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 12px;
  margin-right: 5px;
}

.read-more {
  color: #007bff;
  text-decoration: none;
  font-weight: bold;
}

.read-more:hover {
  text-decoration: underline;
}
</style> 
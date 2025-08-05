---
layout: default
title: 影片與動畫生成工具
permalink: /categories/video-animation-generation/
category_name: 影片與動畫生成
---

# {{ page.category_name }} AI 工具

<p>在這裡，您可以找到各種利用人工智能技術生成影片、製作動畫、轉換影片風格以及生成虛擬人說話的工具。無論是製作行銷影片、教育內容，還是社群短片，這些工具都能助您一臂之力。</p>

---

<div class="tool-grid">
  {% assign current_category_slug = page.permalink | remove: "/categories/" | remove: "/" %}
  {% assign category_tools = site.ai_tools | where_exp:"tool", "tool.categories contains current_category_slug or tool.category == current_category_slug" %}

  {% if category_tools.size > 0 %}
    {% for tool in category_tools %}
      {% include tool_card.html tool=tool %}
    {% endfor %}
  {% else %}
    <p>此分類下暫無工具。</p>
  {% endif %}
</div>
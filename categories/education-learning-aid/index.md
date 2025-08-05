---
layout: default
title: 教育與學習輔助工具
permalink: /categories/education-learning-aid/
category_name: 教育與學習輔助
---

# {{ page.category_name }} AI 工具

<p>此類別專為教育和學習場景設計，提供智能教學、自動解題、語言學習、個性化家教等功能。無論是學生需要輔導、自我學習，還是教師準備課程，這些 AI 工具都能革新學習體驗，提升教育效率。</p>

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
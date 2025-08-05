---
layout: default
title: 圖像與設計生成工具
permalink: /categories/image-design-generation/
category_name: 圖像與設計生成
---

# {{ page.category_name }} AI 工具

<p>在這裡，您可以找到各種利用人工智能技術生成圖像、藝術作品、插畫以及輔助設計的工具。無論是需要創意靈感，還是快速產出視覺內容，這些工具都能助您一臂之力。</p>

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
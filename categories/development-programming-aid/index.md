---
layout: default
title: 開發與程式輔助工具
permalink: /categories/development-programming-aid/
category_name: 開發與程式輔助
---

# {{ page.category_name }} AI 工具

<p>此類別專為開發者和程式設計師設計，提供 AI 驅動的程式碼生成、自動除錯、文件整理以及測試輔助等功能。這些工具旨在加速開發流程，提升程式碼質量，讓開發工作更加高效便捷。</p>

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
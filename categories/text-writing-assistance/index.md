---
layout: default
title: 文字生成與寫作輔助工具
permalink: /categories/text-writing-assistance/
category_name: 文字生成與寫作輔助
---

# {{ page.category_name }} AI 工具

<p>這個類別匯集了各種利用人工智能來協助或自動化文字內容創作的工具。無論是需要快速生成文案、文章、報告，還是進行內容改寫、摘要，這些 AI 寫作助手都能極大提升您的效率和文字品質。</p>

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
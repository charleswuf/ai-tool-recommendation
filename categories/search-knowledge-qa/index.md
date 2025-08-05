---
layout: default
title: 搜尋與知識問答工具
permalink: /categories/search-knowledge-qa/
category_name: 搜尋與知識問答
---

# {{ page.category_name }} AI 工具

<p>此類別提供進階的 AI 搜尋工具，能總結複雜資料、跨網站抓取並整合資訊，以及進行事實查證。無論您是進行學術研究、需要快速查詢資料，還是要在撰寫報告前核對信息，這些工具都能讓您更高效地獲取和驗證知識。</p>

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
---
layout: default
title: 語音處理與配音工具
permalink: /categories/voice-processing-dubbing/
category_name: 語音處理與配音
---

# {{ page.category_name }} AI 工具

<p>此類別涵蓋了所有與 AI 語音技術相關的工具，包括語音轉文字、文字轉語音、語音翻譯、聲音克隆以及智能配音等。這些工具能幫助您高效處理音訊內容，為多媒體專案提供專業級的語音解決方案。</p>

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
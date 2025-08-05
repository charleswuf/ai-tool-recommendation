---
layout: default
title: 音樂與作曲工具
permalink: /categories/music-composition/
category_name: 音樂與作曲
---

# {{ page.category_name }} AI 工具

<p>此類別涵蓋了各種利用 AI 技術來輔助音樂創作、編曲、音頻處理和表演的工具。無論您是專業音樂人、業餘愛好者還是對生成音樂感興趣，這裡都能找到幫助您提升創意和效率的解決方案。這些工具包括 AI 譜曲器、智能混音工具、音頻修復軟體以及虛擬樂器等。</p>

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
---
layout: default
title: 生產力與辦公助理工具
permalink: /categories/productivity-office-assistant/
category_name: 生產力與辦公助理
---

# {{ page.category_name }} AI 工具

<p>此類別涵蓋了各種旨在提升工作效率、自動化日常任務的 AI 工具。從處理會議摘要、草擬電子郵件，到智能任務整理和簡報生成，這些 AI 助手能助您更高效地管理工作流程，節省寶貴時間。</p>

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
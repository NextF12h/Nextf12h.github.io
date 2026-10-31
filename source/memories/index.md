---
title: 记忆
date: 2026-11-01 01:20:00
comments: false
---

照片分两类，点进去看。

{% raw %}
<style>
.mem-hub { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 18px; margin-top: 18px; }
.mem-card { display: block; border-radius: 16px; padding: 26px 22px; text-decoration: none !important;
  background: linear-gradient(135deg, rgba(120,160,255,.16), rgba(255,140,190,.14));
  transition: transform .25s ease, box-shadow .25s ease; }
.mem-card:hover { transform: translateY(-3px); box-shadow: 0 10px 26px rgba(0,0,0,.12); }
.mem-card h2 { margin: 0 0 8px; font-size: 22px; letter-spacing: 2px; }
.mem-card p { margin: 0; font-size: 13px; opacity: .65; }
.mem-ico { font-size: 30px; display: block; margin-bottom: 10px; }
</style>

<div class="mem-hub">
  <a class="mem-card" href="/memories/draw/">
    <span class="mem-ico">✏️</span>
    <h2>作图</h2>
    <p>画过的那些，按时间排。</p>
  </a>
  <a class="mem-card" href="/memories/travel/">
    <span class="mem-ico">🧭</span>
    <h2>旅行</h2>
    <p>去过的地方，按时间排。</p>
  </a>
</div>
{% endraw %}

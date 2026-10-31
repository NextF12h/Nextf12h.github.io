---
title: 旅行
date: 2026-11-01 01:20:00
comments: false
---

[← 回到记忆](/memories/)

{% raw %}
<style>
.mem-month { margin: 26px 0 10px; font-size: 17px; letter-spacing: 3px; opacity: .6; }
.mem-item { display: flex; gap: 14px; margin: 14px 0; align-items: flex-start; }
.mem-time { flex: 0 0 92px; font-size: 12px; opacity: .55; padding-top: 6px; font-variant-numeric: tabular-nums; }
.mem-card { flex: 1; border-radius: 12px; overflow: hidden; background: rgba(127,127,127,.07); }
.mem-card img { width: 100%; display: block; transition: transform .5s ease; }
.mem-card:hover img { transform: scale(1.02); }
.mem-date { padding: 8px 12px; font-size: 13px; opacity: .6; }
.mem-empty { padding: 40px 0; opacity: .55; }
@media (max-width: 768px) { .mem-item { flex-direction: column; } .mem-time { padding: 0 0 4px 4px; } }
</style>

<div id="mem-list"><div class="mem-empty" id="mem-empty">正在翻相册……</div></div>

<script>
(async function () {
  const box = document.getElementById('mem-list');
  const tip = document.getElementById('mem-empty');
  const CAT = 'travel';
  try {
    const r = await fetch('/images/memories/' + CAT + '/index.json?t=' + Date.now());
    const rows = await r.json();
    if (!rows.length) { tip.textContent = '这一类还没有照片。'; return; }
    rows.sort((a, b) => (a.date < b.date ? 1 : -1));
    const groups = {};
    for (const it of rows) {
      const m = it.date.slice(0, 7);
      (groups[m] = groups[m] || []).push(it);
    }
    let html = '';
    for (const m of Object.keys(groups).sort().reverse()) {
      html += '<div class="mem-month">' + m.replace('-', ' 年 ') + ' 月</div>';
      for (const it of groups[m]) {
        html += '<div class="mem-item"><div class="mem-time">' + it.date.slice(11) + '</div>' +
          '<div class="mem-card"><img loading="lazy" src="/images/memories/' + CAT + '/' + it.file + '" alt="' + (it.title || '') + '">' +
          '<div class="mem-date">' + it.date + '</div></div></div>';
      }
    }
    box.innerHTML = html;
  } catch (e) { tip.textContent = '照片清单没取到。'; }
})();
</script>
{% endraw %}

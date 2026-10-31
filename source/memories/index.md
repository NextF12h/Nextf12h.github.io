---
title: 记忆
date: 2026-11-01 01:10:00
comments: false
---

按时间排的照片。新的在上面。

{% raw %}
<style>
.mem-wrap { max-width: 980px; margin: 0 auto; }
.mem-loading { padding: 30px 0; opacity: .6; }
.mem-month { margin: 30px 0 12px; font-size: 18px; letter-spacing: 3px; opacity: .6; }
.mem-item { display: flex; gap: 14px; margin: 14px 0; align-items: flex-start; }
.mem-time { flex: 0 0 96px; font-size: 12px; opacity: .55; padding-top: 6px; font-variant-numeric: tabular-nums; }
.mem-card { flex: 1; border-radius: 12px; overflow: hidden; background: rgba(127,127,127,.07); }
.mem-card img { width: 100%; display: block; transition: transform .5s ease; }
.mem-card:hover img { transform: scale(1.02); }
.mem-date { padding: 8px 12px; font-size: 13px; opacity: .6; }
@media (max-width: 768px) {
  .mem-item { flex-direction: column; }
  .mem-time { padding: 0 0 4px 4px; }
}
</style>

<div class="mem-wrap"><div class="mem-loading" id="mem-loading">正在翻相册……</div><div id="mem-list"></div></div>

<script>
(async function () {
  const box = document.getElementById('mem-list');
  const tip = document.getElementById('mem-loading');
  try {
    const r = await fetch('/images/memories/index.json?t=' + Date.now());
    const rows = await r.json();
    if (!rows.length) { tip.textContent = '还没有照片。'; return; }
    const groups = {};
    rows.sort((a, b) => (a.date < b.date ? 1 : -1));
    for (const it of rows) {
      const m = it.date.slice(0, 7);
      (groups[m] = groups[m] || []).push(it);
    }
    let html = '';
    for (const m of Object.keys(groups).sort().reverse()) {
      html += '<div class="mem-month">' + m.replace('-', ' 年 ') + ' 月</div>';
      for (const it of groups[m]) {
        html += '<div class="mem-item">' +
          '<div class="mem-time">' + it.date.slice(11) + '</div>' +
          '<div class="mem-card"><img loading="lazy" src="/images/memories/' + it.file + '" alt="' + (it.title || '') + '">' +
          '<div class="mem-date">' + it.date + '</div></div></div>';
      }
    }
    box.innerHTML = html;
    tip.remove();
  } catch (e) {
    tip.textContent = '照片清单没取到。';
  }
})();
</script>
{% endraw %}

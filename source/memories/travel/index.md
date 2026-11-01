---
title: 旅行
date: 2026-11-01 01:20:00
comments: false
---

走过的地方。

{%% raw %%}
<style>
.mem-hub {{ display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 18px; margin-top: 18px; }}
.mem-card {{ display: block; border-radius: 16px; padding: 24px 20px; text-decoration: none !important;
  background: linear-gradient(135deg, rgba(120,200,255,.16), rgba(140,255,190,.12));
  transition: transform .25s ease, box-shadow .25s ease; }}
.mem-card:hover {{ transform: translateY(-3px); box-shadow: 0 10px 26px rgba(0,0,0,.12); }}
.mem-card h2 {{ margin: 0 0 6px; font-size: 21px; letter-spacing: 2px; }}
.mem-card p {{ margin: 0; font-size: 13px; opacity: .62; }}
.mem-ico {{ font-size: 28px; display: block; margin-bottom: 8px; }}
.mem-empty {{ padding: 40px 0; opacity: .55; }}
</style>

<div class="mem-hub" id="hub"><div class="mem-empty">正在翻……</div></div>

<script>
(async function () {{
  const hub = document.getElementById('hub');
  try {{
    const r = await fetch('/images/memories/travel/regions.json?t=' + Date.now());
    const rows = await r.json();
    if (!rows.length) {{ hub.innerHTML = '<div class="mem-empty">还没有地方。</div>'; return; }}
    hub.innerHTML = rows.map(x =>
      '<a class="mem-card" href="/memories/travel/' + x.slug + '/">' +
      '<span class="mem-ico">' + (x.ico || '📍') + '</span>' +
      '<h2>' + x.name + '</h2><p>' + (x.count || 0) + ' 张</p></a>').join('');
  }} catch (e) {{ hub.innerHTML = '<div class="mem-empty">没取到。</div>'; }}
}})();
</script>
{%% endraw %%}

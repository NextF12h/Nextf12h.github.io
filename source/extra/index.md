---
title: extra
date: 2026-11-01 12:10:00
comments: false
---

<meta name="robots" content="noindex,nofollow">

{% raw %}
<style>
.gate { max-width: 420px; margin: 80px auto; text-align: center; }
.gate input { width: 100%%; padding: 12px 14px; border-radius: 10px; border: 1px solid rgba(127,127,127,.4);
  background: transparent; color: inherit; font-size: 16px; box-sizing: border-box; }
.gate button { margin-top: 12px; width: 100%%; padding: 12px; border-radius: 10px; border: 0;
  background: rgba(127,127,127,.2); color: inherit; font-size: 16px; cursor: pointer; }
.gate .hint { margin-top: 10px; font-size: 12px; opacity: .5; }
.mem-month { margin: 26px 0 10px; font-size: 17px; letter-spacing: 3px; opacity: .6; }
.mem-item { display: flex; gap: 14px; margin: 14px 0; align-items: flex-start; }
.mem-time { flex: 0 0 92px; font-size: 12px; opacity: .55; padding-top: 6px; }
.mem-card { flex: 1; border-radius: 12px; overflow: hidden; background: rgba(127,127,127,.07); }
.mem-card img { width: 100%%; display: block; }
.mem-date { padding: 8px 12px; font-size: 13px; opacity: .6; }
.mem-empty { padding: 40px 0; opacity: .55; }
</style>

<div id="gate" class="gate">
  <input id="pw" type="password" placeholder="口令" autocomplete="off">
  <button id="go">进去</button>
  <div class="hint" id="hint"></div>
</div>
<div id="mem-list" style="display:none"></div>

<script>
const HASH = '2a9644a5b5a50930209190cbdb71dedac4c3972ee466369ad84910ee2733d28e';
async function sha(s) {
  const b = await crypto.subtle.digest('SHA-256', new TextEncoder().encode(s));
  return [...new Uint8Array(b)].map(x => x.toString(16).padStart(2, '0')).join('');
}
async function load() {
  document.getElementById('gate').style.display = 'none';
  const box = document.getElementById('mem-list');
  box.style.display = '';
  try {
    const r = await fetch('/images/memories/adult/index.json?t=' + Date.now());
    const rows = await r.json();
    if (!rows.length) { box.innerHTML = '<div class="mem-empty">还没有。</div>'; return; }
    rows.sort((a, b) => ((b.date || '') < (a.date || '') ? -1 : (b.date || '') > (a.date || '') ? 1 : 0));
    const groups = {};
    for (const it of rows) {
      const m = it.date ? it.date.slice(0, 7) : '未标日期';
      (groups[m] = groups[m] || []).push(it);
    }
    let html = '';
    for (const m of Object.keys(groups).sort().reverse()) {
      html += '<div class="mem-month">' + (m === '未标日期' ? m : m.replace('-', ' 年 ') + ' 月') + '</div>';
      for (const it of groups[m]) {
        html += '<div class="mem-item"><div class="mem-time">' + (it.date ? it.date.slice(11) : '') + '</div>' +
          '<div class="mem-card"><img loading="lazy" src="/images/memories/adult/' + it.file + '" alt="">' +
          '<div class="mem-date">' + (it.date || '') + '</div></div></div>';
      }
    }
    box.innerHTML = html;
  } catch (e) { box.innerHTML = '<div class="mem-empty">没取到。</div>'; }
}
(async function () {
  if (localStorage.getItem('extra_ok') === HASH) return load();
  document.getElementById('go').onclick = async () => {
    const v = document.getElementById('pw').value;
    if (await sha(v) === HASH) { localStorage.setItem('extra_ok', HASH); load(); }
    else { document.getElementById('hint').textContent = '不对。'; }
  };
  document.getElementById('pw').addEventListener('keydown', e => { if (e.key === 'Enter') document.getElementById('go').click(); });
})();
</script>
{% endraw %}

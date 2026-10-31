---
title: 音乐
date: 2026-10-31 23:59:00
type: music
comments: false
---

常听的那些，扔在这儿。

{% raw %}
<link rel="stylesheet" href="/lib/APlayer.min.css">
<style>
#article-container .aplayer { height: 116px; margin: 18px 0; }
#article-container .aplayer-pic { width: 116px; height: 116px; }
#article-container .aplayer-info { padding: 12px 14px; }
#article-container .aplayer-title { font-size: 17px; font-weight: 600; }
#article-container .aplayer-author { font-size: 13px; }
#article-container .aplayer-time { font-size: 12px; }
#article-container .aplayer-list { max-height: 680px; }
#article-container .aplayer-list ol { padding: 0; }
#article-container .aplayer-list ol li { height: 50px; line-height: 50px; font-size: 15px; }
#article-container .aplayer-list ol li .aplayer-list-index { font-size: 15px; }
#article-container .aplayer-list ol li .aplayer-list-author { font-size: 12px; }
@media (max-width: 768px) {
  #article-container .aplayer { height: 96px; }
  #article-container .aplayer-pic { width: 96px; height: 96px; }
  #article-container .aplayer-title { font-size: 15px; }
}
</style>
<script src="/lib/APlayer.min.js"></script>
<script src="/lib/Meting.min.js"></script>

<meting-js
  server="tencent"
  type="playlist"
  id="9801303096"
  api="https://api.injahow.cn/meting/?server=:server&type=:type&id=:id&r=:r"
  order="random"
  volume="0.7"
  list-folded="false"
  preload="none"
  list-max-height="640px"
  mutex="true"
  fixed="false">
</meting-js>

<noscript>播放器需要 JavaScript。歌单在 <a href="https://y.qq.com/n/ryqq_v2/playlist/9801303096">QQ 音乐</a>。</noscript>
{% endraw %}
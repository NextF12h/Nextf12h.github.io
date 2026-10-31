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
#article-container .aplayer-list { max-height: 70vh; overflow-y: auto; }
#article-container .aplayer-list ol { padding: 0; }
#article-container .aplayer-list ol li { height: 50px; line-height: 50px; font-size: 15px; }
#article-container .aplayer-list ol li .aplayer-list-index { font-size: 15px; }
#article-container .aplayer-list ol li .aplayer-list-author { font-size: 12px; }
@media (max-width: 768px) {
  #article-container .aplayer { height: 96px; }
  #article-container .aplayer-pic { width: 96px; height: 96px; }
  #article-container .aplayer-title { font-size: 15px; }
}
/* new-songs */
.new-title { font-size: 20px; margin: 26px 0 12px; letter-spacing: 2px; }
.new-songs { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 12px; }
.new-song { display: flex; align-items: center; gap: 10px; padding: 8px; border-radius: 10px;
  background: rgba(127,127,127,.08); position: relative; overflow: hidden;
  animation: nsGlow 3.6s ease-in-out infinite; }
.new-song:nth-child(2n) { animation-delay: .9s; }
.new-song:nth-child(3n) { animation-delay: 1.8s; }
@keyframes nsGlow {
  0%, 100% { box-shadow: 0 0 0 rgba(255,120,160,0); }
  50% { box-shadow: 0 0 14px rgba(255,120,160,.45); }
}
.ns-pic { width: 76px; height: 76px; border-radius: 8px; background-size: cover; background-position: center; flex: 0 0 auto; }
.ns-meta { min-width: 0; }
.ns-name { font-size: 16px; font-weight: 600; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.ns-artist { font-size: 13px; opacity: .65; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.ns-badge { position: absolute; right: 8px; top: 8px; font-size: 11px; opacity: .4; }
@media (max-width: 768px) { .new-songs { grid-template-columns: 1fr; } }

/* top-songs */
.top-title { font-size: 20px; margin: 26px 0 12px; letter-spacing: 2px; }
.top-songs { display: flex; flex-direction: column; gap: 8px; }
.top-song { display: flex; align-items: center; gap: 12px; padding: 8px 12px; border-radius: 10px;
  background: rgba(127,127,127,.08); position: relative; overflow: hidden; }
.ts-rank { width: 28px; font-size: 15px; opacity: .55; font-variant-numeric: tabular-nums; }
.ts-pic { width: 52px; height: 52px; border-radius: 8px; background-size: cover; background-position: center; flex: 0 0 auto; }
.ts-meta { min-width: 0; flex: 1; }
.ts-name { font-size: 15px; font-weight: 600; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.ts-artist { font-size: 12px; opacity: .65; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.ts-count { font-size: 15px; font-weight: 700; opacity: .8; }
.ts-shine::after { content: ""; position: absolute; inset: 0;
  background: linear-gradient(110deg, transparent 30%, rgba(255,255,255,.22) 50%, transparent 70%);
  transform: translateX(-100%); animation: tsSweep 3.4s ease-in-out infinite; }
.ts-gold { background: linear-gradient(100deg, rgba(255,210,120,.22), rgba(255,140,90,.16)); }
.ts-gold .ts-rank, .ts-gold .ts-count { color: #d98a2b; opacity: 1; }
@keyframes tsSweep { 0% { transform: translateX(-100%); } 55%, 100% { transform: translateX(100%); } }</style>
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

<!-- NEW-SONGS:BEGIN -->
<h2 class="new-title">最近加入</h2>
<div class="new-songs">
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0005izK54fHRMv')"></div>
      <div class="ns-meta"><div class="ns-name">可愛くてごめん</div><div class="ns-artist">Ado</div></div>
      <span class="ns-badge">01</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=002rbMEl4I1zMG')"></div>
      <div class="ns-meta"><div class="ns-name">星見る頃を過ぎても</div><div class="ns-artist">Mili</div></div>
      <span class="ns-badge">02</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000ANhJ34aANbK')"></div>
      <div class="ns-meta"><div class="ns-name">PPPP (feat. Hatsune Miku, Kasane Teto)</div><div class="ns-artist">TAK/初音未来 (初音ミク)</div></div>
      <span class="ns-badge">03</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=002maNrQ17HV2k')"></div>
      <div class="ns-meta"><div class="ns-name">泡沫の夢</div><div class="ns-artist">ハコニワリリィ</div></div>
      <span class="ns-badge">04</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=003u5LgG0PQssL')"></div>
      <div class="ns-meta"><div class="ns-name">Eutopia</div><div class="ns-artist">Yoohsic Roomz</div></div>
      <span class="ns-badge">05</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0029xmPX0ZF8Kw')"></div>
      <div class="ns-meta"><div class="ns-name">君だけを守りたい</div><div class="ns-artist">中岛文明</div></div>
      <span class="ns-badge">06</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000ZbuVh1LZ9MA')"></div>
      <div class="ns-meta"><div class="ns-name">風のとおり道</div><div class="ns-artist">杉並児童合唱団</div></div>
      <span class="ns-badge">07</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004PDAjM3Bh9Tq')"></div>
      <div class="ns-meta"><div class="ns-name">光の唄</div><div class="ns-artist">大原ゆい子</div></div>
      <span class="ns-badge">08</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000OdfZn0eC42x')"></div>
      <div class="ns-meta"><div class="ns-name">芽吹の唄</div><div class="ns-artist">大原ゆい子</div></div>
      <span class="ns-badge">09</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=')"></div>
      <div class="ns-meta"><div class="ns-name">芽吹の唄</div><div class="ns-artist">大原ゆい子</div></div>
      <span class="ns-badge">10</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004KeYPT3PI6YI')"></div>
      <div class="ns-meta"><div class="ns-name">継承の唄</div><div class="ns-artist">大原ゆい子</div></div>
      <span class="ns-badge">11</span>
    </div>
    <div class="new-song">
      <div class="ns-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004KeYPT3PI6YI')"></div>
      <div class="ns-meta"><div class="ns-name">風と行く道</div><div class="ns-artist">大原ゆい子</div></div>
      <span class="ns-badge">12</span>
    </div>
</div>
<!-- NEW-SONGS:END -->
<!-- TOP-SONGS:BEGIN -->
<h2 class="top-title">常听</h2>
<div class="top-songs">
    <div class="top-song ts-gold">
      <div class="ts-rank">01</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004DRfOZ4QqPmf')"></div>
      <div class="ts-meta"><div class="ts-name">時を刻む唄</div><div class="ts-artist">Lia/VISUAL ARTS/Key Sounds Label (キー・サウンズ・レーベル)</div></div>
      <div class="ts-count">147</div>
    </div>
    <div class="top-song ts-shine">
      <div class="ts-rank">02</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0001AKlN21C2LS')"></div>
      <div class="ts-meta"><div class="ts-name">小さなてのひら</div><div class="ts-artist">riya</div></div>
      <div class="ts-count">131</div>
    </div>
    <div class="top-song ts-shine">
      <div class="ts-rank">03</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0021tIXj2FLlv8')"></div>
      <div class="ts-meta"><div class="ts-name">ツバサ</div><div class="ts-artist">若山詩音</div></div>
      <div class="ts-count">120</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">04</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=003jDl2t0Ba4Q9')"></div>
      <div class="ts-meta"><div class="ts-name">あんずの花</div><div class="ts-artist">すりぃ/ねね</div></div>
      <div class="ts-count">109</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">05</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0001AKlN21C2LS')"></div>
      <div class="ts-meta"><div class="ts-name">潮鳴りⅡ</div><div class="ts-artist">折户伸治</div></div>
      <div class="ts-count">97</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">06</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=003zDEQp0Pz0Aq')"></div>
      <div class="ts-meta"><div class="ts-name">Flower Dance</div><div class="ts-artist">DJ OKAWARI</div></div>
      <div class="ts-count">96</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">07</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=002gTwxp1Oj5XO')"></div>
      <div class="ts-meta"><div class="ts-name">ありがとう…</div><div class="ts-artist">KOKIA</div></div>
      <div class="ts-count">95</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">08</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0001AKlN21C2LS')"></div>
      <div class="ts-meta"><div class="ts-name">潮鳴り</div><div class="ts-artist">折户伸治</div></div>
      <div class="ts-count">91</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">09</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=001QK0a22DsdBA')"></div>
      <div class="ts-meta"><div class="ts-name">夢で逢いましょう</div><div class="ts-artist">SARD UNDERGROUND</div></div>
      <div class="ts-count">87</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">10</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=0008wyPM36i7IV')"></div>
      <div class="ts-meta"><div class="ts-name">星空のバラード</div><div class="ts-artist">真夏龙</div></div>
      <div class="ts-count">86</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">11</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000OvlWJ0vrFZp')"></div>
      <div class="ts-meta"><div class="ts-name">空は高く風は歌う</div><div class="ts-artist">春奈るな</div></div>
      <div class="ts-count">82</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">12</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=002Ir6Sv2lB7Wr')"></div>
      <div class="ts-meta"><div class="ts-name">It&#x27;s only the fairy tale</div><div class="ts-artist">宮村優子</div></div>
      <div class="ts-count">82</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">13</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000Dy9HS1TLM8S')"></div>
      <div class="ts-meta"><div class="ts-name">群青</div><div class="ts-artist">YOASOBI</div></div>
      <div class="ts-count">81</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">14</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=001iuAub2NeYLk')"></div>
      <div class="ts-meta"><div class="ts-name">春はゆく</div><div class="ts-artist">Aimer</div></div>
      <div class="ts-count">80</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">15</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=000xZF0P0g2Ide')"></div>
      <div class="ts-meta"><div class="ts-name">Arrietty&#x27;s Song</div><div class="ts-artist">Cécile Corbel</div></div>
      <div class="ts-count">77</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">16</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004KeYPT3PI6YI')"></div>
      <div class="ts-meta"><div class="ts-name">旅人の唄</div><div class="ts-artist">大原ゆい子</div></div>
      <div class="ts-count">76</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">17</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=004T02kD1ybahm')"></div>
      <div class="ts-meta"><div class="ts-name">unlasting</div><div class="ts-artist">LiSA</div></div>
      <div class="ts-count">76</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">18</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=001sq0x73JFWDG')"></div>
      <div class="ts-meta"><div class="ts-name">spiral</div><div class="ts-artist">LONGMAN</div></div>
      <div class="ts-count">73</div>
    </div>
    <div class="top-song">
      <div class="ts-rank">19</div>
      <div class="ts-pic" style="background-image:url('https://api.injahow.cn/meting/?server=tencent&type=pic&id=00136U1E1X08qe')"></div>
      <div class="ts-meta"><div class="ts-name">Beyond The Time~メビウスの宇宙を越えて~</div><div class="ts-artist">TM NETWORK</div></div>
      <div class="ts-count">72</div>
    </div>
</div>
<!-- TOP-SONGS:END -->


<noscript>播放器需要 JavaScript。歌单在 <a href="https://y.qq.com/n/ryqq_v2/playlist/9801303096">QQ 音乐</a>。</noscript>
{% endraw %}

---
theme: midnight
layout: full
---

# Raw HTML — Custom Layouts & Animation

`::: html` passes content through unchanged (no Markdown parsing). Ideal for SVGs,
timelines, or pure CSS animations.

::: html
<div style="display:flex;gap:0;justify-content:space-between;margin-top:2.5rem;font-family:system-ui,sans-serif">
  <div style="flex:1;text-align:center;position:relative">
    <div style="width:18px;height:18px;border-radius:50%;background:#58a6ff;margin:0 auto;animation:dot 1.6s infinite"></div>
    <div style="height:3px;background:linear-gradient(90deg,#58a6ff,#79c0ff);position:absolute;top:7px;left:50%;width:100%"></div>
    <div style="margin-top:1rem;color:#79c0ff;font-weight:600">Capture</div>
    <div style="color:#8b949e;font-size:.85rem">Markdown</div>
  </div>
  <div style="flex:1;text-align:center;position:relative">
    <div style="width:18px;height:18px;border-radius:50%;background:#a371f7;margin:0 auto;animation:dot 1.6s infinite .2s"></div>
    <div style="height:3px;background:linear-gradient(90deg,#a371f7,#d2a8ff);position:absolute;top:7px;left:50%;width:100%"></div>
    <div style="margin-top:1rem;color:#d2a8ff;font-weight:600">Parse</div>
    <div style="color:#8b949e;font-size:.85rem">Regex Parser</div>
  </div>
  <div style="flex:1;text-align:center;position:relative">
    <div style="width:18px;height:18px;border-radius:50%;background:#3fb950;margin:0 auto;animation:dot 1.6s infinite .4s"></div>
    <div style="height:3px;background:linear-gradient(90deg,#3fb950,#56d364);position:absolute;top:7px;left:50%;width:100%"></div>
    <div style="margin-top:1rem;color:#56d364;font-weight:600">Render</div>
    <div style="color:#8b949e;font-size:.85rem">Theme + CSS</div>
  </div>
  <div style="flex:1;text-align:center">
    <div style="width:18px;height:18px;border-radius:50%;background:#f0a060;margin:0 auto;animation:dot 1.6s infinite .6s"></div>
    <div style="margin-top:1rem;color:#f0a060;font-weight:600">Show</div>
    <div style="color:#8b949e;font-size:.85rem">Full Screen</div>
  </div>
</div>
<style>@keyframes dot { 0%,100% { transform:scale(1);opacity:1 } 50% { transform:scale(1.5);opacity:.5 } }</style>
:::

⚠️ `<script>` doesn't run here — use a dedicated `.html` slide for real JavaScript.

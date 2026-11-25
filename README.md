# Go Gentle Into The Future · xiger 的推荐小屋

把体验过的东西分门别类地放在这儿，像一本书的目录。

在线地址：https://kkk-ugpm.netlify.app

---

## 关于这个网站

该怎么说呢，自述应该是：首先关于这个网站，实际上是一个很久之前就设想的小小项目——我把我体验过的一些事物 share 出来，给每个人。

网站已经用 GitHub 建仓，用 Netlify 上线，目前还没有任何成本。本人学艺不精，还不会 PHP 和 JS，所以网站是用纯 HTML5 + CSS 写的，日后会不断完善。

网站主题「Go Gentle Into The Future」是模仿狄兰·托马斯的《Do Not Go Gentle Into That Good Night》。狄兰所表达的是让父亲不要坦然面对死亡，而我想表达的是：**要坦然接受时代的发展**。

最开始我是在中专时期通过陆明老师接触到的网页制作。当时小鹿子（爱称）带我们用记事本一个一个地打代码，出一点问题就得核对半天；小鹿子只是一味叫我们用记事本，也没告诉我们还有 DW 和 VSCode 这么好用的东西。感谢她带我进入这么一个世界。

上大学后我对网页制作产生了越来越浓厚的兴趣，之前做过一个别的小项目，虽然大部分借助了 AI，有时间我会把它链接进来的。本次网站虽然也用了 DSH，但借助工具完成目的，何尝不是人类的智慧呢。

最后，关于我自己其实没什么好说的，一个分享欲强盛的普通人罢了。希望这个网站能对你有些许帮助！

---

## 目录结构

```
index.html          首页（目录）
css/
  base.css          所有页面共用：底色、标题、卡片、提示、页脚
  CSS.CSS           首页专用：大图 + 菜单渐变
  cssyy.css         音乐页专用：按歌手折叠
tu/                 图片（原图 + thumbs/ 缩略图）
two/                各分类页
```

## 怎么加一个分类

1. 复制 `two/haowu.html`，改名成新分类，改标题和副标题。
2. `<body style="--tint: #xxx">` 换一个卡片渐变收尾色。
3. 首页 `index.html` 的 `.menu1` 里加一行：

```html
<a class="menu-item" href="two/新页面.html">
  <span class="m-title">分类名</span>
  <span class="m-desc">一句话说明</span>
</a>
```

菜单配色由 `css/CSS.CSS` 里的 `:nth-child(n)` 控制，加第十条时补一行即可。

## 卡片怎么写

```html
<main class="cards">
  <article class="card">
    <h2 class="card-title">标题</h2>
    <p class="card-desc">一句介绍。</p>
  </article>
</main>
```

- 想整块可点，把 `article` 换成 `<a class="card" href="…" target="_blank" rel="noopener">`
- 想加一行贴底的价格/说明，用 `<p class="card-price">`
- 列数在 `base.css` 的 `.cards` 里，`repeat(4, minmax(0, 1fr))` 改成别的数字即可；780px 两列、440px 一列

## 部署

Netlify 连本仓库，构建命令留空，发布目录 `.`。缓存策略见 `netlify.toml`（CSS 不缓存，改了刷新就能看到）。

本地预览：直接双击 `index.html`，不需要服务器。

---

© 2026 xiger · Designed by xiger
特别鸣谢：DSH & 陆明老师

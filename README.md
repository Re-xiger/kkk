# xiger 推荐小屋

一个纯静态的个人推荐站，没有框架、没有构建、没有后端。

## 目录

```
index.html          首页（目录）
css/
  base.css          所有页面共用：底色、标题、卡片、焦点样式
  CSS.CSS           首页专用：大图 + 菜单
  cssyy.css         音乐页专用：按歌手折叠
tu/                 图片
two/                九个分类页
```

## 加一个分类

1. 复制 `two/haowu.html`，改名成新分类，改标题和副标题。
2. `<body style="--tint: #xxx">` 换一个卡片渐变收尾色。
3. 首页 `index.html` 的 `.menu1` 里加一行：

```html
<a class="menu-item" href="two/新页面.html">
  <span class="m-title">分类名</span>
  <span class="m-desc">一句话说明</span>
</a>
```

菜单配色由 `CSS.CSS` 里的 `:nth-child(n)` 控制，加第十条时补一行即可。

## 部署

Netlify 连本仓库，构建命令留空，发布目录 `/`。样式和含义见 `netlify.toml`。

## 本地预览

直接双击 `index.html` 即可，不需要服务器。

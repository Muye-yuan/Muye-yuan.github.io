# 如何修改、发布、让搜索引擎搜到，以及如何隐藏

## 1. 修改网页内容

主要改 `index.html`。

- 改名字：搜索 `<h1><strong>Muye</strong> Yuan</h1>`
- 改学校/地点：搜索 `King's College London, London, UK.`
- 改个人介绍：搜索 `I am a <code>KCL student</code>`
- 改头像：搜索 `avatars.githubusercontent.com`
- 改 news：搜索 `<section id="news"`
- 改 research/repository 列表：搜索 `<section id="research"`
- 改底部版权：搜索 `© Copyright 2026 Muye Yuan.`

每次修改后，在浏览器刷新 `http://localhost:4173/index.html` 就能看到变化。

## 2. 让搜索 “Muye Yuan” 能搜到这个网站

本地网址 `localhost` 不会被 Google/Bing 搜到。需要发布到公网。

推荐用 GitHub Pages：

1. 登录 GitHub。
2. 新建仓库，名字必须是：`Muye-yuan.github.io`
3. 把这个文件夹里的 `index.html`、`README.md`、`robots.txt`、`sitemap.xml` 上传到仓库根目录。
4. 进入仓库 `Settings -> Pages`。
5. Source 选择 `Deploy from a branch`，branch 选择 `main`，folder 选择 `/root`。
6. 发布后网址通常是：`https://muye-yuan.github.io/`
7. 去 Google Search Console 添加这个网址，并提交 sitemap：`https://muye-yuan.github.io/sitemap.xml`

搜索引擎收录通常需要几天到几周。页面里已经加入了 `title`、`description`、`canonical`、`robots`、Open Graph 和 JSON-LD 结构化数据，能帮助搜索引擎理解这是 Muye Yuan 的个人主页。

## 3. 修改 SEO 搜索显示内容

在 `index.html` 顶部 `<head>` 里面修改：

- `<title>Muye Yuan</title>`：搜索结果标题
- `<meta name="description" ...>`：搜索结果简介
- `<meta name="keywords" ...>`：关键词
- JSON-LD 里的 `knowsAbout`：你的研究关键词

## 4. 隐藏某一段内容

如果只是暂时不显示某段 HTML，可以用注释包起来：

```html
<!--
这里的内容不会显示在网页上
-->
```

如果想保留代码但不显示，可以给元素加 `hidden`：

```html
<section hidden>
  这里不会显示
</section>
```

## 5. 不让搜索引擎收录整个网站

如果你想隐藏整个网站，不让 Google/Bing 收录：

在 `index.html` 的 `<head>` 里把：

```html
<meta name="robots" content="index, follow">
```

改成：

```html
<meta name="robots" content="noindex, nofollow">
```

同时把 `robots.txt` 改成：

```txt
User-agent: *
Disallow: /
```

最彻底的方法是：关闭 GitHub Pages，或者把仓库改成 private。

## 6. 隐藏 GitHub 上的源码

GitHub Pages 免费个人站一般来自公开仓库，所以别人可以看到源码。要隐藏源码：

- 不用 GitHub Pages，改用支持私有部署的平台。
- 或者升级/使用支持 private Pages 的 GitHub 方案。
- 或者只发布编译后的静态文件，不放个人隐私内容。

不要把手机号、住址、学生号、私人邮箱、API key、密码放到网页或公开仓库里。

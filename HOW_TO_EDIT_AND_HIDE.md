# 网站修改说明

网站采用简洁文字排版，无需安装依赖或构建。直接打开 index.html 即可查看。

## 内容位置

- `index.html` 中 `aside`：姓名、学校、GitHub 和 Google Scholar 链接。
- `id="about"`：博士、硕士经历和导师。
- `id="research"`：研究方向列表。
- `id="news"`：CSC 公派信息，确认获资助时间后再添加日期。
- 出版物暂未显示，之后有论文时可以增加 Publications 栏目。
- `style.css`：字体、间距和手机适配。

## 发布

将 index.html、style.css、robots.txt、sitemap.xml 放在 GitHub Pages 发布目录中。网站地址为 https://muye-yuan.github.io/ 。

身份或研究方向变化时，同步更新 index.html 顶部的 description、Open Graph 和 JSON-LD，并更新 sitemap.xml 中的 lastmod 日期。

## 暂时隐藏内容

在对应 section 上添加 hidden 属性即可隐藏显示，内容仍存在于源码中。私密内容应直接从公开网页和仓库中移除。

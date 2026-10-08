# Shaocheng Liu — 个人学术主页

白底、蓝色链接、桌面双栏、手机单栏的英文静态学术主页。无需安装 Ruby、Jekyll、Node.js 或购买服务器。此包是定制静态模板，不是 al-folio 安装包。

## 先查看

解压后双击 index.html 即可在浏览器中查看。styles.css 与 index.html 必须放在同一目录。正文、DOI 链接和 BibTeX 展开不依赖 JavaScript。

## 发布前补充与核对

- 核对姓名、导师英文名、学院名称及科研经历。
- 添加常用学术邮箱、Google Scholar / ORCID 链接（任选）、头像和英文 CV。
- 补全硕士、本科和两段 RA 的起止年月；目前仅 Ph.D. 标注 2026–present，RA 标注时长。
- 目前只展示已知完整书目信息的两篇 TIT。请提供 ISIT、ITW 的正式题名、作者、会议年份、录用/发表状态和链接，再追加条目。已录用未发表的论文应明确标注 Accepted。
- 页面不写未公开的研究项目名称、奖学金申请结果或未经核实的荣誉。
- 本次做了文件、锚点、BibTeX 和书目信息一致性检查；未做浏览器视觉验收或实际 GitHub 部署。

## 用 GitHub 网页发布（不需要命令行）

1. 登录 https://github.com/ ，点击右上角 + → New repository。
2. Repository name 填 `你的GitHub用户名.github.io`，使用小写用户名。例如用户名是 `shaochengliu`，则填写 `shaochengliu.github.io`。这只是举例，没有确认该用户名可用或属于你。
3. 选择 Public，勾选 Add README，点击 Create repository。
4. 仓库首页点击 Add file → Upload files。将解压后的 index.html、styles.css、publications.bib、README.md 上传到仓库根目录并提交。不要上传 ZIP，也不要把所有文件套在 academic-homepage 子目录下。
5. 上传空文件 `.nojekyll`；如果文件选择器没有显示它，在仓库中点击 Add file → Create new file，文件名填 `.nojekyll`，保持内容为空并提交。
6. 进入 Settings → Pages。Source 选 Deploy from a branch；Branch 选 main；Folder 选 /(root)；点击 Save。
7. 在 Actions 中查看 pages build and deployment 是否完成，然后在 Settings → Pages 点击 Visit site。网址为 `https://你的GitHub用户名.github.io/`。
8. GitHub 官方说明发布更新可能需要最多 10 分钟。若看到 404，先检查 index.html 是否确实在 main 的根目录，再检查 Actions 日志和 Pages 的发布源。

官方文档：
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## 编辑主页

在 GitHub 打开 index.html → 编辑按钮 → 修改 → Commit changes。也可以用 VS Code 在本机修改后重新上传。index.html 控制内容；styles.css 控制字体、颜色和布局；publications.bib 提供论文引用下载。

### 添加照片

建立 assets 文件夹，放入 portrait.jpg。找到 index.html 中的 To add a portrait 注释，将下面这一行插入 h1 之前：

```html
<img class="portrait" src="assets/portrait.jpg" alt="Shaocheng Liu">
```

### 添加联系链接和 CV

在左侧 profile 的 nav 之后添加以下链接，先把占位符替换成真实地址：

```html
<p><a href="mailto:YOUR_EMAIL">Email</a></p>
<p><a href="YOUR_SCHOLAR_URL">Google Scholar</a></p>
<p><a href="YOUR_ORCID_URL">ORCID</a></p>
<p><a href="assets/cv.pdf">Curriculum Vitae</a></p>
```

将真实英文 CV 上传为 assets/cv.pdf 后再添加 CV 链接。没有资料时不添加链接。

### 更新论文

复制 publications 列表中的完整 li 条目，放到相应年份位置。修改题名、作者、期刊/会议信息、DOI 和 details 内的 BibTeX；同时更新 publications.bib。用 strong 只加粗自己的名字。若有适合公开的作者版本 PDF，可上传 assets 文件夹，并在 paper-links 中添加相对路径链接。

### 扩展研究方向

目前以熵区域、组合结构和信息不等式自动证明为主。未来希望展示智能体/世界模型/RL 方向时，可以在 Research Interests 新增 Reinforcement Learning for Language Agents 条目，用公开且稳定的研究描述；成熟后再链接论文或项目页。

### 维护动态

News 仅记录论文发表、录用和学术报告等实际事件。修改页面时也更新 footer 的 Last updated 日期。

## al-folio 选项

如果以后需要大量论文筛选、独立项目页、博客和自动参考文献管理，可以迁移到 al-folio。此版本先用较少的文件提供同样克制的学术外观，搭建步骤更少。不能把本包按 al-folio 的 Jekyll 配置步骤部署，两者是不同路线。

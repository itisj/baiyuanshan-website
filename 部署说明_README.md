# 白猿山 · THE LINE 官网 — 部署包（全英文文件名 · 跨设备安全版）

> ✅ **请用这个文件夹部署**。文件名全部是纯英文（ASCII），可以放心拷到任何电脑 / 上传到任何服务器，媒体不会再丢。

## 为什么之前媒体会缺失？
旧包里有中文 / 带空格的文件名（`配图_精选/`、`logo new/`、`宝马 logo_transparent.png`…）。macOS 用 NFD 方式存中文名、本机查找很宽容；一旦**拷到别的电脑或上传到 Linux 服务器**，文件名编码（NFC/NFD）和空格会对不上，网页里写的路径就找不到文件 → 媒体全部 404。本版已把所有中文/空格文件名与文件夹改成英文，并同步改好全部引用，**根除此问题**。

## 包内容（共 162 个文件，约 245 MB）
| 项 | 说明 |
|---|---|
| `index.html` | 网站入口 |
| `media/` | 138 张图片（作品、团队、明星、奖项、品牌 logo） |
| `clientlogos/` | 7 个客户品牌 logo（滚动条用） |
| `assets/videos/` | 15 个作品视频 |
| `logo_horizontal.png` | 顶栏 / 开场片头白猿山横版 logo |
| `robots.txt` | 允许搜索引擎收录 |

- 已逐一校验：**161 个引用资产全部存在、0 坏链、0 多余文件、文件名 100% 英文。**
- 本地预览：直接双击 `index.html` 即可看（图片全部正常；个别浏览器对 `file://` 本地视频有限制，属正常，**部署到服务器后视频全部可播**）。

## 怎么部署（任选一种）
- **最省事 — Netlify**：打开 https://app.netlify.com/drop ，把本文件夹**整个拖进去** → 出临时网址 → Domain settings 绑你的域名。
- **传统主机（宝塔 / cPanel / nginx / Apache）**：把本文件夹**里面的所有文件**上传到站点根目录（`public_html/` 或 `wwwroot/`）。注意上传"里面的内容"，别把 `theline_website` 外壳也传进去。确认 `index.html` 在根，访问 `https://你的域名/`。
- **GitHub Pages / Vercel** 亦可。

## 上线注意（重要）
1. **别用 Cloudflare Pages 免费版**：单文件上限 25 MB，而最大视频 `cctv_xiaokang.mp4` 有 44 MB 会被拒。GitHub Pages（100MB/文件）/ Netlify / Vercel / 任意 nginx·Apache 都可以。
2. **🇨🇳 字体（国内访问关键）**：字体来自 Google Fonts，国内访问常被墙/很慢。若主要面向国内客户，建议把字体本地化打包进站——**这步我可以帮你做**。
3. **社媒分享缩略图**：上线后把 `index.html` 里 `og:image` 改成绝对地址 `https://你的域名/media/works/chengdu_h.jpg`。
4. **HTTPS / www 跳转**：主机面板一键开启（Let's Encrypt 免费证书）。

---
开场 24fps 动效结束后出现「中文 / English」语言选择；顶栏右上也可随时切换。

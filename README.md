# 🌸 女性成长文案工作台 · GitHub Pages 部署指南

本目录是工作台的**公网版**静态文件（无后端），部署后手机在任意网络都能打开，
不需要开电脑，数据存在手机浏览器里（记得定期导出 JSON 备份）。

## 一、注册 GitHub（5 分钟）

1. 打开 https://github.com 注册账号（邮箱 + 密码，免费）
2. 登录后点右上角头像 → Your repositories

## 二、创建仓库并上传文件（5 分钟）

1. 点绿色按钮 **New repository**
2. 仓库名填一个英文名，例如：`wenzian-gongzuotai`（不能用中文，小写字母/数字/横线）
3. 选 **Public**（公开，免费版 GitHub Pages 要求公开仓库）
4. 点 **Create repository**
5. 进入仓库页面后，点 **uploading an existing file**（上传现有文件）
6. 把本目录里的 5 个文件全部拖进去：`index.html`、`manifest.json`、`icon-180.png`、`icon-192.png`、`icon-512.png`
7. 往下拉点 **Commit changes**

## 三、开启 GitHub Pages（2 分钟）

1. 仓库页面点 **Settings**（设置）
2. 左侧菜单找到 **Pages**（或 Code and automation → Pages）
3. Build and deployment 区域：
   - **Source** 选 **Deploy from a branch**
   - **Branch** 选 `main`，文件夹选 `/ (root)`
   - 点 **Save**
4. 等 1-2 分钟，页面顶部会出现你的地址：

```
https://你的用户名.github.io/wenzian-gongzuotai/
```

> 浏览器打开这个地址，能正常显示工作台就成功了 ✅
> 首次部署可能要等几分钟，期间显示 404 属正常，刷新几次即可。

## 四、手机添加到桌面（2 分钟）

1. 手机浏览器打开上面的地址
2. 安卓 Chrome：右上角菜单 ⋮ → **添加到主屏幕 / 安装应用**
3. iPhone Safari：分享按钮 → **添加到主屏幕**
4. 桌面生成入口，以后点开即用 🎀

## 五、以后更新工作台

只要重新上传 `index.html`（覆盖旧的）即可，GitHub Pages 会自动生效（1-2 分钟）。

---

## ❓ 常见问题

**Q：为什么「🔍 自动读取」在公网版不能点？**
A：抓取小红书/抖音需要后端代理（登录墙 + 跨域限制），GitHub Pages 是纯静态托管，
没有后端。公网版请手动粘贴标题/正文、上传首图。需要一键抓取时，用电脑本地版：
`node 工作台服务器.js` 然后访问 http://localhost:8787。

**Q：手机之前本地版/云沙箱的数据怎么迁过来？**
A：素材库页 → 导出 JSON → 发到手机 → 公网版素材库页 → 导入 JSON。
（数据存在浏览器 localStorage，绑定网址，换网址后是独立的一份）

**Q：想用自己域名？**
A：Settings → Pages → Custom domain 里填你的域名，并按提示到域名服务商加一条 CNAME 记录。

**Q：仓库不想公开？**
A：免费版 GitHub Pages 仅支持公开仓库。想私有部署可换 Cloudflare Pages（免费且支持私有）。

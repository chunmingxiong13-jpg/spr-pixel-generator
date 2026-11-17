# SPR 像素测试图生成器（iPhone 主屏幕版）

本工具是纯静态网页/PWA，无需服务器程序、数据库或用户登录。网站发布为公开链接后，任何人都可以访问；iPhone 用户可添加到主屏幕。

## 文件结构（全部放在仓库根目录）

- `index.html`：SPR 图案生成器
- `manifest.webmanifest`：主屏幕网页应用配置
- `sw.js`：离线缓存 Service Worker
- `icon-192.png`、`icon-512.png`、`apple-touch-icon.png`：应用图标

## 用 iPhone 发布到 GitHub Pages（免费）

1. 在 Safari 打开 https://github.com/ 并登录/注册 GitHub 账号。
2. 点击 `+` → `New repository`，仓库名填 `spr-pixel-generator`。
3. 选择 **Public**，然后创建仓库。
4. 解压本 ZIP。iPhone「文件」App 中点一下 ZIP 文件即可解压出文件夹。
5. 在仓库页面点击 **Add file → Upload files**。
6. 从解压文件夹中上传以下 6 个文件到仓库最外层（不要上传到子文件夹）：
   - `index.html`
   - `manifest.webmanifest`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `apple-touch-icon.png`
7. 点击 **Commit changes**。
8. 打开仓库 **Settings → Pages**。
9. 在 **Build and deployment** 中选择 **Deploy from a branch**。
10. Branch 选 `main`，文件夹选 `/(root)`，点击 **Save**。
11. 等待发布。网站地址通常为：
    `https://你的GitHub用户名.github.io/spr-pixel-generator/`

## iPhone 添加到主屏幕

1. 使用 iPhone 的 Safari 打开 GitHub Pages 网站地址（必须使用发布后的 HTTPS 地址）。
2. 点击分享按钮。
3. 选择 **添加到主屏幕（Add to Home Screen）**。
4. 如果看到 **作为网页 App 打开（Open as Web App）**，将其打开。
5. 点击“添加”。以后从主屏幕图标启动。

## 离线使用

第一次打开网站时保持联网，并等待页面完全加载。Service Worker 会缓存网页和应用图标。随后可尝试关闭网络，再从主屏幕图标启动。首次缓存未完成前不要断网。

## 更新网站

以后修改 `index.html` 或其他文件时，在 GitHub 仓库上传新版本并 Commit。重新联网打开网站，等待更新后关闭并重新打开主屏幕 App。

## 注意

- 仓库必须是 Public，网站和源码对所有人公开；不要上传私人数据。
- SPR 图案在浏览器本地 Canvas 中生成，不会把生成的图像上传到网站服务器。
- PNG 文件像素尺寸由输入宽高决定；手机显示时是否一图像像素对应一面板物理像素，还受设备缩放、显示映射和浏览器设置影响。

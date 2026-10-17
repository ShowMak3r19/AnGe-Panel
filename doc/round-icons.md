# 圆形远程图标

图片图标以圆形、透明底色、无内边距显示，保留原始比例。文字与在线矢量图标不变。图片中圆形以外的内容会被裁切，适合玻璃圆盘图标。

## 使用

1. 在 [图标仓库](https://github.com/ShowMak3r19/circular-glass-icons) 查找图标。
2. 复制原始图片地址，而不是 GitHub 的 `blob` 文件页面地址。例如：
   `https://raw.githubusercontent.com/ShowMak3r19/circular-glass-icons/main/originals/github.png`
3. 编辑导航条目，选择「图片」，将地址粘贴进图片 URL 输入框，保存即可。

图片由浏览器直接请求；浏览器所在网络需能访问图片地址。不会在前端放入 GitHub 访问令牌。图标库公开，文件名和 URL 大小写需一致。

## 发布文件

当前上游的 `src/` 与发布界面样式不一致。此次增加独立样式 `dist/assets/round-icons-v1.css` 并由 `dist/index.html` 引用，不重建或覆盖现有前端包。相同样式保存在 `src/styles/round-icons.css`，供未来恢复源码构建时使用。

更新本补丁时保持两个 CSS 文件一致；样式变更后改用新文件名并同步 HTML 引用，避免浏览器缓存。

## NAS 更新

雾灰紫壁纸使用 `/uploads/wallpapers/glass-mist-desktop-v1.png` 作为背景。竖屏时自动显示同目录下的 `glass-mist-mobile-v1.png`，横屏保持横版图；切换到其他背景时，这条适配规则不会生效。

本 Fork 发布镜像为 `ghcr.io/showmak3r19/ange-panel:latest`。已有部署只需替换 Compose 中的 `image`，保留原端口、数据挂载和其他设置，再拉取镜像并重新部署。

修改已包含在本 Fork 的 Docker 构建上下文中，使用仓库根目录的 Dockerfile 构建镜像即可。更新容器前备份现有持久化数据，并沿用原数据卷和端口映射。此次代码交付不会自动替换现有 NAS 容器或导航配置。

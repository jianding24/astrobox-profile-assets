# 阿呜 · AstroBox 主页资源

用于阿呜 AstroBox 主页的背景、个人介绍卡片与萌宠互动展板。以下为当前维护入口（2026-11-18）。

## 当前入口

| 内容 | 查看与使用 | 修改位置 |
| --- | --- | --- |
| 个人介绍卡片 v9 | [预览](https://jianding24.github.io/astrobox-profile-assets/intro-card-v9/) · [复制安装代码](https://jianding24.github.io/astrobox-profile-assets/intro-card-v9/astrobox-code.txt) | `intro-card-public.zip` → `intro-card-v9/` |
| 萌宠互动展板 v26 | [打开展板](https://jianding24.github.io/astrobox-profile-assets/board-host-test/board-v26/) | `board-host-test-public.zip` → `board-host-test/board-v26/` |
| 主页背景 v2 | [图片地址](https://raw.githubusercontent.com/jianding24/astrobox-profile-assets/refs/heads/main/astrobox-background-v2.png) | `astrobox-background-v2.png` |

个人卡片请复制 TXT 中的完整代码到 AstroBox 自定义展板；预览页不是安装代码。卡片由透明标题 iframe、原生社交链接和箭头 iframe 组成。社交链接保留在 iframe 外。

## 文件与必要依赖

- 可编辑的公开 HTML、CSS、JS 和素材保存在 ZIP 内。修改时解压对应 ZIP，保持相对路径，重新打包并提交。
- 个人卡片 v9 的 `header.html` 依赖 `intro-card-v2/decor-top-v3.png`；安装代码依赖同目录的 `xhs-v2.png`、`afdian.png`。**不要直接删除 v2 目录。**
- 萌宠 v26 的 `index.html`、`board.css`、`app.js` 管理展板；`resource-links.js` 保存作品入口；各 `original-*` 目录和 `board-assets/` 保存试玩及展示资源，需保留内部相对路径。
- `board-v12-public.zip`、host 根展板和历史个人卡片仍在当前发布范围内。它们不是当前推荐入口；移除前需确认旧链接使用情况与依赖。

## 更新与发布

`.github/workflows/pages.yml` 解压三个 ZIP、复制两张背景图片并发布到 GitHub Pages。只修改本 README 不会重新发布网站。

1. 在本地修改对应发布包，检查资源引用、显示和交互。
2. 提交后到 [Actions](https://github.com/jianding24/astrobox-profile-assets/actions) 确认发布成功，并检查线上入口。
3. 如采用新版本路径，在 AstroBox 更新嵌入代码；发布本身不会替换主页中已保存的路径。同路径更新可能受缓存影响。

普通网页预览不等于所有 AstroBox 客户端或表盘真机均已验证。

## 公开范围与许可

这里是**公开的主页展示与限定试玩资源**。浏览器加载的代码和素材可被获取；压缩或混淆不是加密。不要提交账号凭据、密钥、私有完整工程或未计划公开的关卡与素材。

公开可访问不代表授予任意复制、再发布或商业使用许可。第三方字体、图标等以其各自许可证及权利声明为准，发布包中的许可文件应保留；本仓库不以一份统一开源许可覆盖所有资源。

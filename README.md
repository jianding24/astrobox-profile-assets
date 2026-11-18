# 阿呜 · AstroBox 个人主页资源导航

这里集中存放 AstroBox 主页使用的公开背景、个人介绍卡片和萌宠互动展板。**以后从本页找入口，不必翻历史版本。**

> 核对日期：2026-11-18。依据 A_WU 当日公开主页配置和本仓库发布工作流。这里记录的是配置已保存，不代表已完成所有客户端/真机验证。

## 当前使用的入口

| 用途 | 当前版本与入口 | 到哪里修改 |
| --- | --- | --- |
| 顶部个人介绍卡片 | [v9 预览](https://jianding24.github.io/astrobox-profile-assets/intro-card-v9/) · [手机复制代码 TXT](https://jianding24.github.io/astrobox-profile-assets/intro-card-v9/astrobox-code.txt) | `intro-card-public.zip` 内的 `intro-card-v9/` |
| 萌宠互动展板 | [v26 展板](https://jianding24.github.io/astrobox-profile-assets/board-host-test/board-v26/) | `board-host-test-public.zip` 内的 `board-host-test/board-v26/` |
| 主页背景 | [当前背景 v2](https://raw.githubusercontent.com/jianding24/astrobox-profile-assets/refs/heads/main/astrobox-background-v2.png) | 根目录 `astrobox-background-v2.png` |

**当前配置已保存 v9**：个人卡片引用 `intro-card-v9/header.html?v=1`、`intro-card-v9/arrow.html`，萌宠引用 `board-host-test/board-v26/`。背景使用上面的 Raw 图片地址。没有把预览页 `index.html` 整页嵌入主页。

## 个人卡片：预览和安装代码不是同一回事

- `intro-card-v9/index.html`：原版与新版本对照，供检查；不是安装代码。
- `intro-card-v9/astrobox-code.txt`：在手机打开，全选复制，粘贴到 AstroBox 自定义展板。
- `intro-card-v9/snippet.html`：同一份嵌入 HTML 源码。
- `intro-card-v9/header.html`：透明山景和标题；山景相对 v8 下移 4px，文字位置不变。
- `intro-card-v9/arrow.html`：独立的扁平双箭头动画，固定 20px 高。
- `intro-card-v9/sanitized.html`：按 AstroBox v2.2.5 官方处理规则生成的回归检查输出，不应替代原始安装代码。

**重要共用依赖，不要删除旧目录：** v9 的山景仍引用 `intro-card-v2/decor-top-v3.png`；小红书和爱发电图标仍引用 `intro-card-v2/xhs-v2.png`、`intro-card-v2/afdian.png`。`intro-card-v2` 不是可以直接删除的“无用旧版”。

社交链接位于 iframe 外的原生 HTML 中，保持可点击；标题与动态装饰放在 iframe 中。不要把外链按钮移入受限 iframe。不要把 `<img` 复制成 `< img`，也不要把 `href` 改为空格。

## 萌宠展板维护位置

v26 目录主要文件：

- `index.html`：展板结构、三个系列 tab、双作品入口。
- `board.css`：布局、透明背景、字体及按钮外观。
- `app.js`：系列切换、嵌入试玩页、尺寸通知与资源跳转处理。
- `resource-links.js`：三个快应用和三个配套表盘的 AstroBox 资源地址。
- `original-cat/`：喵伴展示页和配套表盘素材。
- `original-sort/`：萌宠归队限定试玩及表盘。
- `original-bubble/`、`original-bubble-face/`：萌宠泡泡堂试玩及表盘。
- `board-assets/`：共用视觉素材、字体和 `FONT-LICENSE.txt`。

网页可浏览到的 HTML/JS/CSS 是公开展示版本，不等于可随意公开完整私有工程。完整开发工程不在本导航中发布；本次整理未重新审计所有游戏逻辑是否已最小化。

## 仓库文件与部署关系

| 根目录文件 | 用途 |
| --- | --- |
| `intro-card-public.zip` | 个人卡片各公开版本及共用资源，部署时解压至网站根目录 |
| `board-host-test-public.zip` | 萌宠展板，部署时提取其中 `board-host-test/` 目录 |
| `board-v12-public.zip` | 早期公开展板包，仍被工作流解压；未确认无依赖前不要删除 |
| `astrobox-background.png` | 旧背景，保留历史链接 |
| `astrobox-background-v2.png` | 当前主页背景 |
| `.github/workflows/pages.yml` | GitHub Actions 构建与 Pages 发布配置 |

目前可编辑的公开源码放在 ZIP 内，而不是仓库根目录展开。修改时先下载并解压对应 ZIP，保持原相对路径，改完重新打包。不要只改解压出来的本地文件却漏传 ZIP。

工作流依次解压两份展板包、复制两张背景、解压个人卡片包，生成 `_site` 并发布 Pages。**只改 README 不会触发 Pages 部署**，本页本身在 GitHub 仓库内查看。

## 安全更新流程

1. 保留当前在用路径和旧资源，不移动、不删除。
2. 新设计先放新版本目录，在预览中检查透明、文字、图标、尺寸和外链。
3. 提交对应 ZIP 后，在 [Actions](https://github.com/jianding24/astrobox-profile-assets/actions) 确认发布成功。
4. 打开公开预览和 TXT，确认不是 404，检查版本路径与代码内容。
5. 用户确认后，才在 AstroBox 替换嵌入代码；发布新版本本身不会自动替换主页配置。

同路径内容更新可能受浏览器或 CDN 缓存影响；已观测 Pages 响应含 `cache-control: max-age=600`。优先使用独立版本目录，必要时给复制链接增加查询版本参数。**不能仅凭显示未更新就断言是缓存**，还需检查已保存代码里的路径。

## 历史版本与验证边界

- v1–v4：早期视觉、透明实现和无图标兼容测试，保留链接；v2 中部分素材仍为当前依赖。
- v6：紧凑版、动态扁箭头。
- v7：继续压缩链接上下留白。
- v8：将链接上方 4px 留白移到下方，总高度不变。
- v9：只将山景装饰下移 4px；当前已保存到 A_WU 主页配置。
- v5 未作为公开采用版本发布，不要依据编号假定存在可用页面。

v9 已通过官方处理器回归及普通浏览器视觉/资源检查。当前已保存不代表 AstroBox 所有机型、外链行为和窄屏自动高度均完成实机验证；对照预览页也不完全等同于客户端宿主。浏览器正常不代表原生 GMF、Lua 或表盘真机能力已验证。

## 公开范围提醒

此仓库和 GitHub Pages 是公开的，浏览器加载的脚本、图片和字体都能被获取。压缩或混淆不是加密，也不能保证素材或玩法不可被复刻。不要上传口令、令牌、账号凭据、私有源工程、完整关卡库或不打算公开的资源；发布前检查 ZIP 清单，保留必要的字体/图标许可。未经核查，不要把某个历史包当作可以删除的备份。

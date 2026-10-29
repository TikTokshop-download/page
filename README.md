# TikTok Shop 合作方服务页面

纯静态、多语言的合作方介绍与应用下载页面，无需数据库、PHP 或前端构建工具。

## 页面入口

| 页面 | 语言 |
| --- | --- |
| `index.html` | English |
| `cn.html` | 简体中文 |
| `fr.html` | Français |
| `de.html` | Deutsch |
| `it.html` | Italiano |
| `es.html` | Español |
| `ko.html` | 한국어 |
| `jp.html` | 日本語 |
| `ms.html` | Bahasa Melayu |
| `th.html` | ภาษาไทย |

十个 HTML 页面共用 `assets/` 内的样式、脚本和两张插图。部署时必须包含整个 `assets/` 目录。

## 配置

编辑 `assets/config.js`，按实际情况填写：

- `operator`：运营主体全称。
- `contactEmail`：联系邮箱。
- `relationshipUrl`：真实可核验的合作关系说明链接。
- `privacyUrl`：隐私政策链接。
- `publisher`：应用实际发布者。
- `androidUrl`、`iosUrl`：Android APK 与 iOS 外部分发入口。

目前的下载地址沿用原页面。运营主体、联系方式、应用发布者与合作说明尚未填写，需要在上线前补齐和核实。页面不宣称软件已经通过安全认证，也不验证合作资质。

下载由用户主动触发，确认弹窗展示目标地址和发布者信息；两个系统的入口分别标注，不使用 App Store 图标指代外部分发。

## 本地预览

可直接打开 HTML 文件。如果已安装 Python，也可以在仓库根目录运行：

```shell
python -m http.server 8080 --bind 127.0.0.1
```

浏览器打开 `http://127.0.0.1:8080/cn.html`。

## 宝塔部署

将十个 HTML 文件及整个 `assets/` 目录上传到宝塔站点根目录即可，默认首页为英文 `index.html`。如需默认显示中文，在站点的默认文档设置中将 `cn.html` 排在 `index.html` 之前。

## 维护与验证

- 外观：`assets/site.css`。
- 语言切换和下载确认交互：`assets/site.js`。
- 各语言正文：对应 HTML 文件。
- 保留所有访客一致可见的内容，不包含安全检测分流或隐藏内容。
- 前端改版不会自动解除浏览器已有的危险网站警告。请核实安装包、外部跳转和运营信息，按需申请官方复核。

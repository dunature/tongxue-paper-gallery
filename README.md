# 仝学 · 书页与长廊

独立的 10 套融合视觉选型图库，每套包含首页、科研成果、能力中心、论文服务。

- 浏览入口：`public/index.html`
- 完整中文说明：`public/DESIGN.md`
- 生成提示词：`prompts.json`
- 原始图像与映射：`public/images`、`asset-manifest.json`
- 浏览器验收：`evidence/verify-gallery.mjs` 与验收 JSON

本图库是静态设计图、局部氛围动效与真实图库控件的组合。图片里的业务功能为视觉示意。

本地预览：`python3 -m http.server 8744 --bind 127.0.0.1 --directory public`

Render 静态站点：构建命令 `true`，发布目录 `public`。图片响应头须配置 `Cache-Control: public, max-age=0, s-maxage=300, no-transform`，确保原始 PNG 不被 CDN 转换。

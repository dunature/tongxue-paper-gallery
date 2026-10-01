# 仝学融合图库验收记录

验收日期：2026-10-01。

## 发布前验收：通过

- 实际点击 10 套 × 4 页，共 40 个组合；标题、图像、当前页面、设计解析、原图与下载链接同步。
- 每套均验证整套对比与四张卡片返回单页、暂停与恢复光效、原像素与铺满、原图新窗口、PNG 下载、上一套与下一套。
- 每套完整中文解析默认可见，位于设计图或整套对比下方。
- 6 次快速连续切换：加载时立即隐藏旧图，显示当前目标的加载提示，最终图像与最后选择一致。
- 模拟一次图片请求失败：错误提示及重试正常，恢复后显示正确页面。
- 390 × 844、DPR 3 手机布局无页面级横向溢出；完整解析可阅读。
- DESIGN.md 下载内容与源文件一致；各套 PNG 实际下载内容与原文件哈希一致。
- 40 张 PNG 均与内置图像工具输出逐字节一致；视觉联系表已复核四页用途及风格延续。

证据：`local-audit.json`、`local-mobile.png`、`local-design-notes.png`；复现脚本 `verify-gallery.mjs`（修改开头的 TaskSpace id 与 base 即可切换验收环境），使用已有 ego-browser，不引入测试框架。

## 发布后验收：通过

独立网址：https://tongxue-paper-gallery.onrender.com/

部署版本：`dc4728581931dd42d825a7a680f16dfdd02a4531`，Render 部署 `dep-dav7dg142hec73daei0g`，状态 live。

- 40 张线上 PNG 全部与本地原图 SHA-256 一致，响应类型均为 `image/png`。
- 图片响应包含 `Cache-Control: public, max-age=0, s-maxage=300, no-transform`，禁止 CDN 改写图片。
- 线上 HTML、JS、CSS、DESIGN.md 与品牌图标均与本地文件一致。
- 原图库入口文件与原仓库文件一致，原仓库保持干净。
- 线上再次实际点击 40 页及全部类型控件，10 套完整通过；重复验证快速连续切换、失败重试、手机布局与 DESIGN.md 下载。
- 品牌首页链接、左右方向键、系统减少动态时默认暂停及手动恢复均通过。

证据：`public-assets.json`、`public-files.json`、`deployment.json`；原图复现命令：`python3 evidence/verify-public-assets.py https://tongxue-paper-gallery.onrender.com`。

## 验收边界

图库控件与氛围动效已验收。图片内业务按钮、论文图表、3D 应用和咨询服务为静态视觉示意；不表示已实现生产业务或完成研究验证。原有图库及仓库保持不变。

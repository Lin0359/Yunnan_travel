# 云南旅行计划网站

这是一个适合 GitHub Pages 发布、微信打开、并且方便 OpenClaw 后续维护的静态网页模板。

## 文件结构

- `index.html`：网页外观和交互，不建议频繁改。
- `data.json`：旅行数据，后续主要改这个文件。

## OpenClaw 修改原则

后续请优先修改 `data.json`，不要直接改 `index.html`。

常见修改：

- 改城市日期：修改 `routes[].segments` 里的 `start` 和 `duration`
- 增加酒店：修改 `cities.城市名.hotels`
- 增加景点：修改 `cities.城市名.spots`
- 增加美食：修改 `cities.城市名.food`
- 增加链接：给对应项目填写 `link`

`start` 表示从第几天开始，`duration` 表示持续几天。
例如：`start: 5, duration: 3` 表示从第5天开始，连续3天。

## GitHub Pages

上传到 GitHub 仓库后，在 Settings → Pages 中启用 GitHub Pages，选择 main branch / root。

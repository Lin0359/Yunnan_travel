# 云南旅行计划（GitHub Pages）

单页应用，所有内容由 `data.json` 驱动，适合队友/AI 直接维护。

## 目录结构

```
Yunnan_travel/
├── index.html      # 渲染逻辑 + 样式 + 前端脚本
├── data.json       # 行程与城市数据
└── README.md       # 使用说明
```

## data.json 结构

```json
{
  "meta": {
    "title": "页面标题",
    "subtitle": "副标题",
    "days": ["6/22", "6/23", ...],
    "hint": "提示文案"
  },
  "plans": [
    {
      "id": "main",
      "name": "主方案",
      "segments": [
        {"cityId": "xishuangbanna", "label": "西双版纳", "startDay": 1, "duration": 3, "color": "#8fd3a6"},
        {"cityId": "kunming", "label": "昆明", "startDay": 4, "duration": 1, "color": "#a9c7ff"}
      ]
    }
  ],
  "cities": [
    {
      "id": "xishuangbanna",
      "name": "西双版纳",
      "summary": "概述",
      "hotels": [{"name": "酒店", "price": "￥", "note": "说明", "link": "url"}],
      "spots": [{"name": "景点", "price": "￥", "note": "说明"}],
      "food": [{"name": "美食", "price": "人均", "note": "说明"}],
      "transport": [{"day": "Day1", "note": "安排"}],
      "budget": "预算备注"
    }
  ]
}
```

- `meta.days` 控制时间轴列数；
- `plans` 可添加多个方案，`segments` 描述某城市从第几天开始、持续几天；
- `cityId` 需与 `cities` 列表的 `id` 对应；
- `optional: true` 可标记“备选”色块；
- 任意字段留空即可显示“待补充”。

## 本地预览

GitHub Pages 支持直接访问 `index.html`，不需要构建工具。若需本地调试可使用任意静态服务器（如 `python -m http.server`）。

## 更新流程

1. 修改 `data.json` 补充酒店/景点/预算等信息；
2. 如需调整样式或交互，只改 `index.html`；
3. 提交前可本地预览确认；
4. Push 到 GitHub 后，Pages 将自动生效。

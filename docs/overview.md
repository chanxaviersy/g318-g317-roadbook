# 📊 行程总览

本文档提供 30 天行程的全景视图，包括里程、海拔、阶段分布的交互式图表。

---

## 🗓️ 五阶段总览

<div class="stat-bar">
<div class="stat-item">
<div class="stat-value">5</div>
<div class="stat-label">总阶段</div>
</div>
<div class="stat-item">
<div class="stat-value">30</div>
<div class="stat-label">总天数</div>
</div>
<div class="stat-item">
<div class="stat-value">8,800</div>
<div class="stat-label">总公里</div>
</div>
<div class="stat-item">
<div class="stat-value">293</div>
<div class="stat-label">日均公里</div>
</div>
</div>

---

## 📈 阶段里程分布

```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "五阶段里程与天数对比",
  "data": {
    "values": [
      {"stage": "第一阶段\n南行入川", "distance": 1940, "days": 5, "route": "G4→G55→G76→G75→G4215"},
      {"stage": "第二阶段\nG318川藏南线", "distance": 2150, "days": 9, "route": "G318+G4218"},
      {"stage": "第三阶段\n拉萨与延伸", "distance": 1650, "days": 5, "route": "G349+G318"},
      {"stage": "第四阶段\nG317川藏北线", "distance": 2400, "days": 8, "route": "G317+G109"},
      {"stage": "第五阶段\n凯旋东归", "distance": 1600, "days": 3, "route": "G93→G65→G5513→G4"}
    ]
  },
  "encoding": {"x": {"field": "stage", "type": "nominal", "axis": {"labelAngle": 0}}},
  "layer": [
    {
      "mark": {"type": "bar", "cornerRadiusEnd": 8, "width": 50},
      "encoding": {
        "y": {"field": "distance", "type": "quantitative", "title": "里程 (km)"},
        "color": {
          "field": "stage",
          "type": "nominal",
          "scale": {"range": ["#00897b", "#1565c0", "#f57c00", "#6a1b9a", "#43a047"]},
          "legend": null
        }
      }
    },
    {
      "mark": {"type": "text", "align": "center", "baseline": "bottom", "dy": -8, "fontSize": 13, "fontWeight": "bold"},
      "encoding": {
        "y": {"field": "distance", "type": "quantitative"},
        "text": {"field": "distance", "type": "quantitative"}
      }
    }
  ]
}
```

---

## 🏔️ 全程海拔曲线

```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "全程海拔变化曲线",
  "data": {
    "values": [
      {"name": "皇岗", "alt": 50, "stage": 1},
      {"name": "广州", "alt": 200, "stage": 1},
      {"name": "桂林", "alt": 500, "stage": 1},
      {"name": "贵阳", "alt": 900, "stage": 1},
      {"name": "成都", "alt": 1500, "stage": 1},
      {"name": "康定", "alt": 2560, "stage": 2},
      {"name": "理塘", "alt": 4014, "stage": 2},
      {"name": "稻城", "alt": 3750, "stage": 2},
      {"name": "亚丁", "alt": 4600, "stage": 2},
      {"name": "芒康", "alt": 3875, "stage": 2},
      {"name": "然乌", "alt": 3280, "stage": 2},
      {"name": "林芝", "alt": 2900, "stage": 2},
      {"name": "拉萨", "alt": 3650, "stage": 3},
      {"name": "羊湖", "alt": 4990, "stage": 3},
      {"name": "珠峰", "alt": 5248, "stage": 3},
      {"name": "那曲", "alt": 4500, "stage": 4},
      {"name": "昌都", "alt": 3500, "stage": 4},
      {"name": "德格", "alt": 3260, "stage": 4},
      {"name": "雀儿山", "alt": 5050, "stage": 4},
      {"name": "色达", "alt": 4000, "stage": 4},
      {"name": "马尔康", "alt": 2600, "stage": 4},
      {"name": "重庆", "alt": 500, "stage": 5},
      {"name": "张家界", "alt": 300, "stage": 5},
      {"name": "长沙", "alt": 100, "stage": 5},
      {"name": "皇岗", "alt": 50, "stage": 5}
    ]
  },
  "layer": [
    {
      "mark": {"type": "area", "line": true, "point": true, "tooltip": true, "interpolate": "monotone"},
      "encoding": {
        "x": {"field": "name", "type": "nominal", "axis": {"labelAngle": -45, "labelFontSize": 10}, "sort": null, "title": "地点"},
        "y": {"field": "alt", "type": "quantitative", "title": "海拔 (m)"},
        "color": {
          "field": "stage",
          "type": "nominal",
          "scale": {"range": ["#00897b", "#1565c0", "#f57c00", "#6a1b9a", "#43a047"]},
          "legend": {"title": "阶段"}
        }
      }
    },
    {
      "mark": {"type": "rule", "color": "#999", "strokeDash": [4, 4]},
      "encoding": {"y": {"datum": 3000}}
    },
    {
      "mark": {"type": "rule", "color": "#c62828", "strokeDash": [4, 4]},
      "encoding": {"y": {"datum": 5000}}
    }
  ]
}
```

---

## 🛣️ 道路编号里程分布

```vega-lite
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "各道路编号里程占比",
  "data": {
    "values": [
      {"road": "G318 川藏南线", "km": 2150, "type": "国道"},
      {"road": "G317 川藏北线", "km": 2400, "type": "国道"},
      {"road": "G4 京港澳", "km": 1250, "type": "高速"},
      {"road": "G4215 蓉遵", "km": 480, "type": "高速"},
      {"road": "G76 厦蓉", "km": 560, "type": "高速"},
      {"road": "G227 张孟线", "km": 280, "type": "国道"},
      {"road": "G109 京拉线", "km": 450, "type": "国道"},
      {"road": "G349 察芒线", "km": 220, "type": "国道"},
      {"road": "G65 包茂", "km": 520, "type": "高速"},
      {"road": "G4218 雅康", "km": 320, "type": "高速"},
      {"road": "G75 兰海", "km": 360, "type": "高速"},
      {"road": "G93 成渝环线", "km": 340, "type": "高速"},
      {"road": "G55 二广", "km": 480, "type": "高速"},
      {"road": "G5513 长张", "km": 350, "type": "高速"}
    ]
  },
  "mark": {"type": "bar", "cornerRadiusEnd": 6},
  "encoding": {
    "y": {"field": "road", "type": "nominal", "sort": "-x", "title": "道路"},
    "x": {"field": "km", "type": "quantitative", "title": "里程 (km)"},
    "color": {
      "field": "type",
      "type": "nominal",
      "scale": {"domain": ["高速", "国道"], "range": ["#0288d1", "#d32f2f"]},
      "legend": {"title": "类型"}
    },
    "tooltip": [
      {"field": "road", "type": "nominal"},
      {"field": "km", "type": "quantitative", "title": "里程 (km)"},
      {"field": "type", "type": "nominal"}
    ]
  }
}
```

---

## 📅 30天日历视图

| 日期 | Day | 路线 | 起点→终点 | 里程 | 关键 |
|------|-----|------|-----------|------|------|
| 10/19 | 1 | <span class="road-badge road-badge-g4">G4</span><span class="road-badge road-badge-g55">G55</span> | 皇岗→桂林 | 620km | 黄姚古镇 |
| 10/20 | 2 | — | 桂林深度 | 0km | 漓江、阳朔 |
| 10/21 | 3 | <span class="road-badge road-badge-g76">G76</span><span class="road-badge road-badge-g75">G75</span> | 阳朔→贵阳 | 560km | 荔波小七孔 |
| 10/22 | 4 | <span class="road-badge road-badge-g75">G75</span><span class="road-badge road-badge-g4215">G4215</span> | 贵阳→泸州 | 480km | 遵义、茅台镇 |
| 10/23 | 5 | <span class="road-badge road-badge-g4215">G4215</span><span class="road-badge road-badge-g93">G93</span> | 泸州→成都 | 280km | 整备日 |
| **10/24** | **6** | <span class="road-badge road-badge-g4218">G4218</span> | 成都→康定 | 320km | 折多山、泸定桥 |
| 10/25 | 7 | <span class="road-badge road-badge-g318">G318</span> | 康定→理塘 | 290km | 新都桥 |
| 10/26 | 8 | <span class="road-badge road-badge-g227">G227</span> | 理塘→亚丁 | 250km | 珍珠海 |
| 10/27 | 9 | — | 亚丁深度 | 0km | 牛奶海、五色海 |
| 10/28 | 10 | <span class="road-badge road-badge-g318">G318</span> | 稻城→芒康 | 380km | 金沙江大桥 |
| 10/29 | 11 | <span class="road-badge road-badge-g318">G318</span> | 芒康→八宿 | 370km | 72道拐 |
| 10/30 | 12 | <span class="road-badge road-badge-g318">G318</span> | 八宿→波密 | 170km | 然乌湖 |
| 10/31 | 13 | <span class="road-badge road-badge-g318">G318</span> | 波密→林芝 | 230km | 南迦巴瓦 |
| 11/1 | 14 | <span class="road-badge road-badge-g318">G318</span> | 林芝→拉萨 | 470km | 巴松措 |
| 11/2 | 15 | — | 拉萨休整 | 0km | 布达拉宫 |
| 11/3 | 16 | <span class="road-badge road-badge-g349">G349</span> | 拉萨→羊湖 | 220km | 羊卓雍措 |
| 11/4 | 17 | <span class="road-badge road-badge-g318">G318</span> | 拉萨→日喀则 | 280km | 扎什伦布寺 |
| 11/5 | 18 | <span class="road-badge road-badge-g318">G318</span> | 日喀则→珠峰 | 600km | 珠峰大本营 |
| 11/6 | 19 | <span class="road-badge road-badge-g318">G318</span> | 日喀则→拉萨 | 280km | 返程 |
| 11/7 | 20 | <span class="road-badge road-badge-g109">G109</span> | 拉萨→那曲 | 450km | 纳木措 |
| 11/8 | 21 | <span class="road-badge road-badge-g317">G317</span> | 那曲→索县 | 380km | 藏北草原 |
| 11/9 | 22 | <span class="road-badge road-badge-g317">G317</span> | 索县→丁青 | 370km | — |
| 11/10 | 23 | <span class="road-badge road-badge-g317">G317</span> | 丁青→昌都 | 230km | 强巴林寺 |
| 11/11 | 24 | <span class="road-badge road-badge-g317">G317</span> | 昌都→德格 | 340km | 德格印经院 |
| 11/12 | 25 | <span class="road-badge road-badge-g317">G317</span> | 德格→甘孜 | 380km | 雀儿山、新路海 |
| 11/13 | 26 | <span class="road-badge road-badge-g317">G317</span> | 甘孜→色达 | 230km | 喇荣五明佛学院 |
| 11/14 | 27 | <span class="road-badge road-badge-g317">G317</span> | 色达→马尔康 | 380km | 卓克基土司官寨 |
| 11/15 | 28 | <span class="road-badge road-badge-g317">G317</span> | 马尔康→成都 | 340km | 桃坪羌寨 |
| 11/16 | 29 | <span class="road-badge road-badge-g93">G93</span> | 成都→重庆 | 340km | 洪崖洞 |
| 11/17 | 30 | <span class="road-badge road-badge-g65">G65</span><span class="road-badge road-badge-g5513">G5513</span> | 重庆→张家界 | 520km | 武隆天坑 |
| 11/18 | 31 | <span class="road-badge road-badge-g5513">G5513</span> | 张家界→长沙 | 350km | 武陵源 |
| 11/19 | 32 | <span class="road-badge road-badge-g4">G4</span> | 长沙→皇岗 | 600km | 凯旋 |

---

## ⚡ 关键数据卡片

### 🏔️ 海拔相关

| 指标 | 数值 | 备注 |
|------|------|------|
| 最高点 | <span class="altitude altitude-extreme">5248m</span> | 嘉措拉山口（珠峰段） |
| 第二高点 | <span class="altitude altitude-extreme">5130m</span> | 东达山（G318） |
| 第三高点 | <span class="altitude altitude-extreme">5050m</span> | 雀儿山（G317） |
| 5000m+垭口 | **6个** | 折多山/东达山/嘉措拉/雀儿山/岗巴拉/米拉山 |
| 平均住宿海拔 | 3,200m | 多数在低海拔过渡 |

### ⛽ 充电相关

| 指标 | 数值 |
|------|------|
| G318理想5C站点 | 12座 |
| G317理想5C站点 | 0座（国网桩替代） |
| 沿线充电站总数 | 50+ |
| 单次最长补电间隔 | 280km（德格段） |
| 第三方桩最快功率 | **600kW**（马尔康） |
| 理想5C最快功率 | **520kW**（理县服务区） |

### 💰 费用预算（估算）

| 项目 | 金额（元） | 备注 |
|------|----------|------|
| 高速过路费 | ~1,500 | 理想L9 Livis 2.0T 增程 |
| 油费（增程器） | ~3,000 | 西藏段油价较高 |
| 电费 | ~1,200 | 公共桩1.5元/度 |
| 住宿（30晚） | ~12,000 | 拉萨/日喀则较贵 |
| 餐饮 | ~4,500 | 每人150元/天 |
| 门票 | ~1,200 | 亚丁/珠峰等 |
| **合计** | **~23,400** | 单车单人估算 |

---

## 🎯 每日核心目标

!!! info "🟢 第一阶段（Day 1-5）：稳扎稳打"
    - **目标**：从皇岗到成都，不赶路，享受沿途风景
    - **关键**：桂林深度、贵阳美食、茅台镇品酒、成都整备
    - **节奏**：日均 388 km，轻松

!!! info "🔵 第二阶段（Day 6-14）：G318挑战"
    - **目标**：G318全线 + 亚丁深度
    - **关键**：折多山、72道拐、然乌湖、南迦巴瓦峰
    - **节奏**：日均 277 km（含亚丁停留2天）

!!! info "🟠 第三阶段（Day 15-19）：拉萨与巅峰"
    - **目标**：布达拉宫 + 羊湖 + 珠峰
    - **关键**：高原反应预防，嘉措拉山口 5248m
    - **节奏**：日均 330 km

!!! info "🟣 第四阶段（Day 20-27）：G317秘境"
    - **目标**：川藏北线穿越 + 色达佛国
    - **关键**：雀儿山、新路海、喇荣五明佛学院
    - **节奏**：日均 343 km

!!! info "🟢 第五阶段（Day 28-30）：凯旋东归"
    - **目标**：成都→重庆→张家界→长沙→皇岗
    - **关键**：洪崖洞、张家界国家森林公园
    - **节奏**：日均 533 km（赶路，但有5C护航）

---

## 📍 下一步

- 📋 查看 [行前准备](preparation.md) 了解详细准备工作
- 🛣️ 查看 [路线与道路编号](routes.md) 了解全程路网
- ⚡ 查看 [充电站网络](charging.md) 了解补能规划

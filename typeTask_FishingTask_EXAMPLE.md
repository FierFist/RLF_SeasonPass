# 📄 捕捉指定鱼类任务添加示例（FishingTask）

下面说明如何为 **FishingTask（钓鱼任务）** 添加任务。  
详细参数请查看附加配置文件：**config_FishingTasksList.json**

---

## 🧩 typeTask = FishingTask 的额外参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 需要捕获该鱼类的次数，达到此数量后任务完成。 |

---

## 🔧 第一步：在 TASKS 文件夹添加主任务

主任务写在 TASKS 文件夹内，例如：

```json
{
    "taskID": 700,
    "givePoints": 1000,
    "typeTask": "FishingTask",
    "iconTask": "relife_SeasonPass/images/reward_empty.edds",
    "titleTask": "捕获鲤鱼",
    "descTask": "捕获鲤鱼 5 次。",
    "taskParamNumber": [
        5.0
    ],
    "taskParamText": []
}
```

说明：

- `iconTask` 可使用占位图，也可使用自己的图标。
- `taskParamNumber` 表示玩家需要捕捉鲤鱼 5 次。

---

## 🔧 第二步：在 config_FishingTasksList.json 添加附加参数

该配置用于指定：

- 使用哪些鱼竿才算有效  
- 指定哪些鱼（可以多个）  
- 使用什么鱼钩  
- 是否必须在特定位置钓鱼  

```json
{
    "taskID": 700,
    "fishingRod": [],
    "fishTypes": [
        "Carp"
    ],
    "hookTypes": [],
    "placePositions": [],
    "placePositionsRadius": []
}
```

说明：

- `fishingRod` 留空 → 任意鱼竿都有效  
- `fishTypes` 填 `"Carp"` → 只有钓到鲤鱼才算  
- `hookTypes` 留空 → 任意鱼钩有效  
- `placePositions` 留空 → 任意位置均可钓取  
- `placePositionsRadius` 为空时无需区域判定  

---


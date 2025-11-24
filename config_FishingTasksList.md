# 📄 config_FishingTasksList.json 配置说明

该配置用于为 **FishingTask（钓鱼任务）** 类型设置额外参数。

当玩家捕获到符合条件的鱼时，任务将自动计数。

系统支持 **穿透式匹配**：  
也就是说——  
你可以为同一种鱼设置多个任务，并通过不同参数区分（例如不同鱼竿、不同地点、不同次数）。  
系统会同时识别和正确统计。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 任务唯一 ID（来自 TASKS 文件夹） |
| `fishingRod` | `string array` | 要求使用的鱼竿类名列表。如果为空 → 任何鱼竿都可计数。不支持继承，必须写准确类名。 |
| `fishTypes` | `string array` | 可计数的鱼类名列表。如果为空 → 捕获任何鱼都算。不支持继承。 |
| `hookTypes` | `string array` | 鱼竿 Hook 槽位（“Hook”）中所需的钩子类名（如 Hook、WoodenHook、Lure）。为空 → 任何钩子都可计数，不支持继承。 |
| `placePositions` | `vector array` | 指定必须钓鱼的地点（向量：X,Y,Z）。为空 → 任意地点。 |
| `placePositionsRadius` | `vector array` / `float array` | 上述地点的检测半径。数组长度必须与 placePositions 一致。 |

---

## 🧱 配置示例

### 示例 1 — 指定鱼类，无位置要求，无钓竿要求

```json
{
    "taskID": 754,
    "fishingRod": [],
    "fishTypes": [
        "Carp"
    ],
    "hookTypes": [],
    "placePositions": [],
    "placePositionsRadius": []
}
```

---

### 示例 2 — 对钓竿、鱼类、钩子、地点都有限制的复杂任务

```json
{
    "taskID": 755,
    "fishingRod": [
        "CustomFish"
    ],
    "fishTypes": [
        "Carp",
        "More Fish"
    ],
    "hookTypes": [
        "Hook",
        "WoodenHook"
    ],
    "placePositions": [
        [12633.258789, 1.924003, 2457.495605],
        [12633.258789, 1.924003, 2457.495605],
        [12633.258789, 1.924003, 2457.495605]
    ],
    "placePositionsRadius": [
        110,
        50,
        500
    ]
}
```

---


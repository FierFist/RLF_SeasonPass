# 📄 config_KillEntityTasksList 配置说明

该配置用于为 **KillEntity（击杀任务）** 类型添加额外参数。

任务在玩家 **击杀动物 / 玩家 / 僵尸** 时计数，可配合距离、武器类型等条件精确过滤。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹） |
| `needItemInHands` | `string array` | 击杀时玩家手中必须持有的物品类名列表（为空则不限制） |
| `distanceKill` | `int array` | 杀敌距离限制：<br>• `[ -1, -1 ]` → 无限制（任何距离都计数）<br>• 第 1 项 = 最大距离（如 `50` → 仅 50 米内击杀有效）<br>• 第 2 项 = 最小距离（如 `10` → 仅 10 米以上击杀有效）<br>两者可同时使用，判断击杀距离是否落在范围内 |
| `isKindOfEntity` | `bool` | 是否启用继承判断（`IsKindOf`），允许匹配父类（如 AnimalBase、ZombieBase 等） |
| `entityNames` | `string array` | 被允许的目标类名列表（精准类名或继承类均可） |

---

## ⚠ 距离判断逻辑总结

| 配置 | 效果 |
|------|------|
| `[-1, -1]` | 不限制距离 |
| `[50, -1]` | 只要距离 ≤ 50 米就算 |
| `[-1, 20]` | 只要距离 ≥ 20 米就算 |
| `[100, 30]` | 距离必须在 30–100 米之间 |

---

## 🧱 配置示例

```json
{
    "taskID": 1,
    "needItemInHands": [],
    "distanceKill": [
        -1,
        -1
    ],
    "entityNames": [
        "Animal_BosTaurusF_Brown"
    ]
}
```

---


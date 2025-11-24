# 📄 config_ActionTasksList 配置说明

该配置用于为 **ActionComplete** 类型的任务指定附加参数。

此类型任务的特点是：  
⭐ **当玩家执行某个动作（Action）时，任务进度 +1。**

系统具有 **穿透式匹配机制**，意味着：

- 同一个动作可以对应多个不同任务  
- 这些任务可以通过「手上持有的物品」或「需要执行次数」区分  
- 系统会自动识别并正确累计任务进度  

例如：  
- 使用铲子 **挖虫子 5 次**  
- 使用刀 **挖虫子 2 次**  
两个任务可以同时存在，系统会区别统计。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 该配置对应的任务 ID（来自 **TASKS 文件夹中的任务列表**） |
| `actionName` | `string` | 触发任务进度的动作类名（SingleUseBase、ContiniousBase、InteractBase 等）<br>⚠ 不支持没有“完成事件”的动作（如果某个动作不计数，可以问我确认） |
| `needItemInHands` | `string` 或 `string[]` | 计数动作时玩家手中必须持有的物品类名<br>如果为空 → **不限制物品** |

---

## 🧩 特殊说明：ActionHarvestCrops（收获作物）

对于收获类动作，你可以 **指定作物类型**，从而细分任务：

例如：  
- “收获土豆”  
- “收获辣椒”  

只需在 `needItemInHands` 参数中填写 **对应作物的类名**：

示例截图：

<img width="397" height="177" alt="image" src="https://github.com/user-attachments/assets/1490218c-d640-4416-945b-d78dbc0df536" />

---

## 🧱 配置示例

```json
{
    "taskID": 42,
    "actionName": "ActionDigWorms",
    "needItemInHands": [
        "Shovel"
    ]
}
```

---


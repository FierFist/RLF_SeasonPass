# 📄 config_CollectItemsTasksList 配置说明

该配置用于为 **CollectItems** 类型的任务设置额外参数。  
该任务在玩家背包中拥有指定数量的物品时计为完成。

---

## 🧩 TaskCollectItems 参数说明

| 参数 | 类型 | 说明 |
|------|------|------|
| **taskID** | `int` | 任务的唯一 ID（来自 TASKS 文件夹） |
| **deleteItems** | `bool` | 若为 `true`，交付任务时会从玩家背包中删除所有用于完成任务的物品 |
| **collectItemConfig** | `array<TaskCollectItem>` | 收集条件数组 |

---

## 🧩 TaskCollectItem 参数说明

| 参数 | 类型 | 说明 |
|------|------|------|
| **countItem** | `int` | 需要收集的物品数量 |
| **enableIsKindOf** | `bool` | 若为 `true`，通过 `IsKindOf` 判断是否属于该类型；为 `false` 时必须完全匹配类名 |
| **typeItems** | `array<string>` | 可接受的物品类名列表 |
| **typeItemsIgnore** | `array<string>` | 需要忽略的物品类名列表 |

---

## 🧱 配置结构和示例

### 示例 1 — 简单的食物收集任务  
玩家需要收集水果。  
所有物品在提交任务后都会被删除。

```json
{
    "taskID": 1,
    "deleteItems": true,
    "collectItemConfig": [
        {
            "countItem": 5,
            "enableIsKindOf": true,
            "typeItems": ["Apple", "Banana", "Plum"],
            "typeItemsIgnore": ["RottenApple"]
        }
    ]
}
```

---

### 示例 2 — 收集武器但不删除  
玩家背包中只需拥有任意一种武器，提交任务后物品保留。

```json
{
    "taskID": 2,
    "deleteItems": false,
    "collectItemConfig": [
        {
            "countItem": 1,
            "enableIsKindOf": false,
            "typeItems": ["M4A1", "AKM", "FAL"],
            "typeItemsIgnore": []
        }
    ]
}
```

---

### 示例 3 — 多类型物品  
玩家需要收集食物和饮料，提交时全部删除。

```json
{
    "taskID": 3,
    "deleteItems": true,
    "collectItemConfig": [
        {
            "countItem": 3,
            "enableIsKindOf": true,
            "typeItems": ["Apple", "Banana", "Plum", "Zucchini"],
            "typeItemsIgnore": []
        },
        {
            "countItem": 2,
            "enableIsKindOf": true,
            "typeItems": ["WaterBottle", "Canteen"],
            "typeItemsIgnore": []
        }
    ]
}
```

---

### 示例 4 — 精确匹配物品，并排除特定物品  
玩家需要收集 10 罐牛肉罐头，但腐烂版本不算。

```json
{
    "taskID": 4,
    "deleteItems": true,
    "collectItemConfig": [
        {
            "countItem": 10,
            "enableIsKindOf": false,
            "typeItems": ["CannedBeef"],
            "typeItemsIgnore": ["CannedBeef_Rotten"]
        }
    ]
}
```

---

### 示例 5 — 按类别收集  
玩家需要同时拥有任意一把步枪和任意一件医疗用品。  
提交任务时不删除物品。

```json
{
    "taskID": 5,
    "deleteItems": false,
    "collectItemConfig": [
        {
            "countItem": 1,
            "enableIsKindOf": true,
            "typeItems": ["Rifle_Base"],
            "typeItemsIgnore": []
        },
        {
            "countItem": 1,
            "enableIsKindOf": true,
            "typeItems": ["FirstAidKit", "BandageDressing"],
            "typeItemsIgnore": []
        }
    ]
}
```

---


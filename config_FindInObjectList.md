# 📄 config_FindInObjectList 配置说明

该配置用于为 **FindInObject** 类型的任务（来自 *relife_ObjectSearch* 模组）设置附加参数。

任务将会在玩家 **从指定可搜刮对象中找到指定物品** 时完成。

---

示例字段：
```
"seasonPassIDConfig": "RLF_Lootable_Picture",
"findedItems": []
```

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹中的任务列表） |
| `seasonPassIDConfig` | `string` | 来自 relife_ObjectSearch 的可搜刮对象配置 ID |
| `findedItems` | `array<string>` | 需要找到的物品类名列表（任意一个满足即可） |

---

## 🧱 配置示例

```json
[
    {
        "taskID": 954,
        "seasonPassIDConfig": "RLF_Lootable_Picture",
        "findedItems": [
            "Apple"
        ]
    }
]
```

---


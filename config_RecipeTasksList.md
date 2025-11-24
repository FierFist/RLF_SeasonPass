# 📄 config_RecipeTasksList 配置说明

该配置用于为 **RecipeCraft（制作任务）** 类型添加额外参数。

当玩家 **通过配方或工作台制作某个物品** 时，会增加任务进度。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹） |
| `recipeName` | `string` | 配方类名或工作台制作配方的 ID。<br>当玩家执行这个配方时，任务计数 +1（如果任务 taskParamNumber > 1，则需要制作多次） |

---

## 🧱 配置示例

```json
{
    "taskID": 43,
    "recipeName": "CraftRagRope"
}
```

---


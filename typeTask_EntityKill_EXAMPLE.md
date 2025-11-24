# 📄 击杀目标任务添加示例（EntityKill）

下面说明如何为 **EntityKill（击杀任务）** 类型添加任务。  
详细参数请参阅附加配置文件：**config_KillEntityTasksList.json**

---

## 🧩 typeTask = EntityKill 的额外参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 需要击杀的数量。 |
| `taskParamText` | `string array` | 将要显示在任务界面中的生物类名（显示在任务图标旁）。 |

---

## 🔧 第一步：在 TASKS 文件夹内添加主任务

主任务写在 TASKS 内的任务列表文件中，例如：

```json
{
    "taskID": 1,
    "givePoints": 40,
    "typeTask": "EntityKill",
    "iconTask": "relife_SeasonPass/images/reward_empty.edds",
    "titleTask": "家常牛肉",
    "descTask": "使用任意武器击杀一头棕色母牛。",
    "taskParamNumber": [
        1.0
    ],
    "taskParamText": [
    ]
}
```

你可以：

- 保留占位图像（reward_empty.edds）
- 自定义图片路径
- 或使用模组附带的动物图标（路径如下）：

```
relife_SeasonPass/images/task_icons/animals/文件名.edds
```

例如使用熊图标：

```
relife_SeasonPass/images/task_icons/animals/bear.edds
```

示例预览图：

![image](https://github.com/user-attachments/assets/053700ae-b134-4054-ac17-e3df3778b1aa)

---

## 🔧 第二步：在 config_KillEntityTasksList.json 中添加附加参数

该附加配置决定：

- 哪些生物被允许计数  
- 是否需要特定武器  
- 距离限制  
- 是否启用继承（IsKindOf）

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

说明：

- `needItemInHands` 空 → 可用任何武器 / 工具 / 空手击杀均有效  
- `distanceKill` 为 `[-1, -1]` → 不限制击杀距离  
- `entityNames` → 必须击杀 `Animal_BosTaurusF_Brown`（棕色母牛）

---

## 🎥 更详细的视频教程（俄语）
https://youtu.be/f8G-KXa2kyA

---


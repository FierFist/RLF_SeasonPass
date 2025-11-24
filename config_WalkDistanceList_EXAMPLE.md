# 📄 步行距离任务添加示例（WalkDistance）

下面说明如何添加 **步行指定距离** 的任务。  
详细参数请查看附加配置文件：**config_WalkDistanceList.json**

---

## 🧩 额外参数说明（typeTask = WalkDistance）

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 玩家需要步行的距离（单位：米）。用于界面正确显示任务需求。 |

---

## 🔧 第一步：在 TASKS 文件夹添加主任务配置

在 TASKS 文件夹中加入以下任务（主任务文件）：

```json
{
        "taskID": 1500,
        "givePoints": 1000,
        "typeTask": "WalkDistance",
        "iconTask": "relife_SeasonPass/images/task_icons/location.edds",
        "titleTask": "一步一步",
        "descTask": "用自己的双脚走完 1200 米。",
        "taskParamNumber": [
            1200.0
        ],
        "taskParamText": [
        ]
}
```

---

## 🔧 第二步：在 config_WalkDistanceList.json 添加附加参数

用于将任务 ID 与附加配置关联：

```json
{
        "taskID": 1500
}
```

---


# 📄 动作执行任务添加示例（ActionComplete）

下面说明如何为 **动作执行类任务（ActionComplete）** 添加任务。  
详细参数请查看附加配置文件：**config_ActionTasksList.json**

---

## 🧩 额外参数说明（typeTask = ActionComplete）

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 玩家需要执行该动作的次数，达到此数量后任务完成。 |

---

## 🔧 第一步：在 TASKS 文件夹添加主任务配置

主任务放在 TASKS 文件夹中，示例如下：

```json
{
    "taskID": 42,
    "givePoints": 1000,
    "typeTask": "ActionComplete",
    "iconTask": "relife_SeasonPass/images/task_icons/zmb_kill.edds",
    "titleTask": "挖掘大师",
    "descTask": "挖掘 5 次虫子。",
    "taskParamNumber": [
        5.0
    ],
    "taskParamText": []
}
```

---

## 🔧 第二步：在 config_ActionTasksList.json 添加附加参数

由于这是动作相关任务，需要在附加配置中指定动作类名，以及执行任务时是否需要特定物品在手中。

```json
{
    "taskID": 42,
    "actionName": "ActionDigWorms",
    "needItemInHands": []
}
```

> 注意：  
> - `taskID` 必须与主任务的 `taskID` 完全一致  
> - `actionName` 为 DayZ 动作类名  
> - `needItemInHands` 若为空数组，则此动作可用任何物品或空手触发任务  

---

## 🎥 详细教学视频（俄语）
如果你仍然不确定如何添加任务，这里有更详细的教程：  
https://youtu.be/N1IO-jqqAFg

---


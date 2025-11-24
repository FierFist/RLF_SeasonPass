# 📄 通过脚本或外部模组激活任务的示例

下面说明如何添加一种 **可通过脚本主动触发（JustActive）** 的任务。  
适用于你自己的模组或第三方模组，例如：  
你有一个自制的“工作台模组”，想让玩家在工作台上制作物品时完成任务 —— 就可以使用这种任务类型。

---

## 🧩 typeTask = JustActive 的额外参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 要执行任务的次数。达到该次数后任务完成。 |

---

## 🔧 第一步：在 TASKS 文件夹添加主任务

主任务配置示例（TASKS 文件夹中的配置文件）：

```json
{
    "taskID": 666,
    "givePoints": 40,
    "typeTask": "JustActive",
    "iconTask": "relife_SeasonPass/images/reward_empty.edds",
    "titleTask": "在工作台上制作",
    "descTask": "在工作台上制作任意物品 5 次",
    "taskParamNumber": [
        5.0
    ],
    "taskParamText": [
    ]
}
```

说明：

- `taskID = 666` 是你将在脚本中触发的任务 ID
- 任务本身不关联动作、鱼竿、区域等，仅靠脚本触发即可

---

## 🔧 第二步：在你的模组代码中触发任务

由于这种任务是“纯脚本触发的任务”，  
SeasonPass 无法自动知道你在做什么，需要 **手动触发**。

在你的模组某个事件（例如工作台制作完成之后）调用：

```csharp
... 你的工作台制作逻辑代码

    player.AddTaskParam(this, "JustActive", "666|+");

...
```

解释：

- `"JustActive"` —— 任务类型
- `"666|+"` ——  
   - **666** = 任务 ID  
   - **+** = 任务进度 +1  

每执行一次工作台制作动作，就执行一次该代码，任务进度 +1。

---


# 📄 任务配置说明（位于 profile\RELIFE\SEASONPASS\TASKS）

你可以自由命名这些 JSON 文件（使用拉丁字母）。  
关键是：**文件结构必须正确**。  
可以参考已有示例。

该配置用于：

- 储存所有任务
- 系统会根据任务 ID 给玩家分配每日任务、每周任务、赛季任务
- 部分任务需要额外参数，并依赖其他配置文件（见下文说明）

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 任务的唯一 ID |
| `givePoints` | `int` | 完成任务后给予的经验值 |
| `givePointsPremium` | `int` | Premium 玩家额外获得的经验值 |
| `disableBoostBonus` | `bool` | 是否禁用经验加成（Boost） |
| `boostBonusPoints` | `int` | 经验加成数值覆盖（替代百分比 Boost） |
| `allowChangeAfterComplete` | `bool` | 是否允许任务完成后仍可更换 |
| `typeTask` | `string` | 任务类型（必须指定，对应不同扩展配置） |
| `iconTask` | `string` | 图标路径（*.edds 文件） |
| `titleTask` | `string` | 任务标题 |
| `descTask` | `string` | 任务描述（玩家需要完成的行为） |
| `taskParamNumber` | `float array` | 数字型任务额外参数（不同任务类型用途不同） |
| `taskParamText` | `string array` | 字符串型任务额外参数（不同任务类型用途不同） |

---

## 🚧 任务类型（typeTask）

下列链接指向各自的配置说明：

| 任务类型 | 描述 |
|---------|------|
| [EntityKill](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_KillEntityTasksList.md) | 击杀指定生物（动物、僵尸、玩家） |
| [ActionComplete](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_ActionTasksList.md) | 执行某个行动 |
| [RecipeCraft](https://github.com/virusomanvs/relife_SeasonPass/blob/main/typeTask_RecipeCraft_EXAMPLE.md) | 使用原版或工作台进行制作 |
| [LocationCheck](https://github.com/virusomanvs/relife_SeasonPass/blob/main/typeTask_LocationCheck_EXAMPLE.md) | 访问指定地点 |
| [FishingTask](https://github.com/virusomanvs/relife_SeasonPass/blob/main/typeTask_FishingTask_EXAMPLE.md) | 捕捉特定鱼类 |
| [JustActive](https://github.com/virusomanvs/relife_SeasonPass/blob/main/typeTask_JustActive_EXAMPLE.md) | 仅激活任务（给外部模组使用） |
| [CollectItems](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_CollectItemsTasksList.md) | 收集指定物品 |
| [DriveTransport](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_DriveTransportList_EXAMPLE.md) | 开车行驶指定距离 |
| [WalkDistance](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_WalkDistanceList_EXAMPLE.md) | 徒步行走指定距离 |
| [CollectItems](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_TimeInServerList_EXAMPLE.md) | 在服务器中停留时间 |

---

## 🧱 JSON 配置示例

```json
{
    "taskID": 1,
    "givePoints": 40,
    "disableBoostBonus": 0,
    "givePointsPremium": 0,
    "boostBonusPoints": 0,
    "allowChangeAfterComplete": 0,
    "typeTask": "EntityKill",
    "iconTask": "relife_SeasonPass/images/reward_empty.edds",
    "titleTask": "家常牛肉",
    "descTask": "使用任意武器杀死一头棕色奶牛。",
    "taskParamNumber": [
        1.0
    ],
    "taskParamText": [
        "Animal_BosTaurusF_Brown"
    ]
}
```

---

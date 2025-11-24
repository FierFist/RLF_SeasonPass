# 📄 奖励列表配置说明（位于 profile\RELIFE\SEASONPASS\REWARDS）

你可以自由命名这些 JSON 文件（使用拉丁字母）。  
关键点是：**文件内部结构必须严格符合格式。**

你可以参考模组内提供的示例文件。

该配置用于：

- 指定玩家达到某个等级后可以领取的奖励  
- 所有奖励集中在这些 JSON 文件中  
- 在 Season Pass 配置中只引用奖励的 ID  
- 你也可以根据奖励类型，将奖励拆分到多个 JSON 文件中  

⚠ **注意：所有 rewardUniqueID 必须唯一，绝对不能重复！**

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `rewardUniqueID` | `int` | 奖励的唯一 ID，不能重复 |
| `className` | `string` | 物品的 ClassName，或特殊参数（如技能经验） |
| `moreTextInfo` | `string` | 额外说明文字 |
| `itemCount` | `int/array` | 掉落数量：<br>• 第 1 个参数为固定数量<br>• 如果为 -1，则使用随机最小值（第 2 个参数）和最大值（第 3 个参数） |
| `itemHealth` | `float/array` | 物品耐久度（0–1）：用法同上（固定值或随机 min/max） |
| `itemQuantity` | `float/array` | 物品数量百分比（0–1）：用法同上；如果是 **弹匣（Magazine）** 则填写实际子弹数量 |
| `itemIsMagazine` | `bool` | 是否为武器弹匣（用于处理附件正确生成） |
| `transportFillSpawn` | `bool` | 如果物品为 “车辆或船只”，启用此项后会自动加满油并加水（记得给载具配置散热器） |
| `spawnMode` | `int` | 奖励生成方式：<br>• `0` = 掉落在地上<br>• `1` = 放入玩家背包 |
| `attachmentItems` | `array` | 物品附件列表（支持递归生成） |

---

## 📺 配置讲解视频
https://youtu.be/wSWD7LFa1Do

---

## 🎯 与 **Perks & Skills System (RELIFE)** 联动

你可以选择 **不给物品，而给玩家技能经验点数**。

方法：

- 在 `className` 中写：  
  **RELIFEPERKPOINTS_HUNTING**（HUNTING 可换成其他技能）
- 在 `itemQuantity[0]` 填写要给予的经验点数  
- 图标会自动从系统中加载，无需配置

示例：

![image](https://github.com/user-attachments/assets/44322495-e0be-43d2-848d-3e718728e194)

```json
{
    "rewardUniqueID": 2001,
    "className": "RELIFEPERKPOINTS_HUNTING",
    "itemHealth": [1.0, -1.0, -1.0],
    "itemQuantity": [20.0, -1.0, -1.0],
    "itemIsMagazine": 0,
    "attachmentItems": []
},
{
    "rewardUniqueID": 2002,
    "className": "RELIFEPERKPOINTS_MEDICAL",
    "itemHealth": [1.0, -1.0, -1.0],
    "itemQuantity": [35.0, -1.0, -1.0],
    "itemIsMagazine": 0,
    "attachmentItems": []
}
```

---

## ⭐ 与 **DayZ-Expansion-Hardline** 联动

你也可以选择 **不给物品，而给玩家 Hardline 声望（Reputation）**。

方法：

- 在 `className` 中写：  
  **HardlineReputation**
- 在 `itemQuantity[0]` 填入给玩家的声望值
- 图标自动生成，无需配置

![image](https://github.com/user-attachments/assets/48f6b2b9-9107-4cf7-b9b2-03279176dbc1)

```json
{
    "rewardUniqueID": 2000,
    "className": "HardlineReputation",
    "itemHealth": [1.0, -1.0, -1.0],
    "itemQuantity": [1000.0, -1.0, -1.0],
    "itemIsMagazine": 0,
    "attachmentItems": []
}
```


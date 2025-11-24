# 📄 config_PointsCardConfig 配置说明

该配置用于设置各种“卡片”的效果，例如：

- 激活经验加成（Boost）
- 直接给予经验
- 提升等级
- 增加多个等级
- 重置任务更换次数

你可以自定义自己的 ClassName，只要物品支持 **ActionActivateSeasonCard** 行为即可。

模组内包含多种颜色的卡片：

| 物品名称 | 预览 | 物品名称 | 预览 |
|---------|------|----------|------|
| RLF_BattlePass_Points_Iron | <img src="https://github.com/user-attachments/assets/ec28465f-ed90-4b0f-b458-1a682734f173" width="100" height="100"> | RLF_BattlePass_Points_Purple | <img src="https://github.com/user-attachments/assets/1e5a2224-2e0d-4902-bef6-ae93e6f80142" width="100" height="100"> |
| RLF_BattlePass_Points_Silver | <img src="https://github.com/user-attachments/assets/739e9c90-1497-4ea3-8d13-7ef634a15bbb" width="100" height="100"> | RLF_BattlePass_Points_Green | <img src="https://github.com/user-attachments/assets/ecf4851d-26b8-410d-9f64-0401ca1e535e" width="100" height="100"> |
| RLF_BattlePass_Points_Red | <img src="https://github.com/user-attachments/assets/29915333-5e8a-48fc-a52c-65df7b2785c8" width="100" height="100"> | RLF_BattlePass_Points_Blue | <img src="https://github.com/user-attachments/assets/18e433e6-513c-44f6-bb65-51f4c127abc6" width="100" height="100"> |

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `RLF_BattlePass_Points_Iron` | `string` | 卡片或任何包含 ActionActivateSeasonCard 行为的物品类名 |
| `givedPoints` | `integer` | 若未启用 isLevelUpgrade 或 isBoostCard，则使用时直接给予多少经验 |
| `isLevelUpgrade` | `bool` | 启用后，该卡片用于升级等级或直接提升等级（不能与 isBoostCard、isResetTaskAttempt 同时开启） |
| `isBoostCard` | `bool` | 启用后，该卡片用于激活经验加成（不能与 isLevelUpgrade、isResetTaskAttempt 同时开启） |
| `isResetTaskAttempt` | `bool` | 启用后，该卡片用于重置任务更换次数（不能与其他两项同时启用） |
| `attemptType` | `int` | 重置的任务类型：0=每日，1=每周，2=赛季 |
| `boostCoef` | `float` | 经验加成系数，例如 0.25=25% 额外经验 |
| `boostTimeMin` | `int` | 加成持续时间（分钟） |
| `delayToNextUse` | `int` | 冷却时间（分钟）。为 0 则可无限使用 |
| `upgradeLevel` | `int array` | `[目标等级, 增加等级数]`：<br>• 第 1 项 ≠ -1 → 使用后直接提升到指定等级<br>• 第 2 项 ≠ -1 → 增加指定等级数 |

---

## 🎥 视频讲解（俄语）
https://youtu.be/HQjvbqP8vac

---

## 🧱 配置示例

```json
{
    "RLF_BattlePass_Points_Iron": {
        "givedPoints": 100,
        "isLevelUpgrade": 0,
        "delayToNextUse": 0,
        "upgradeLevel": [
            2,
            -1
        ]
    },
    "RLF_BattlePass_Points_Silver": {
        "givedPoints": 100,
        "isLevelUpgrade": 1,
        "delayToNextUse": 0,
        "upgradeLevel": [
            2,
            -1
        ]
    },
    "RLF_BattlePass_Points_Purple": {
        "givedPoints": 100,
        "isLevelUpgrade": 1,
        "delayToNextUse": 0,
        "upgradeLevel": [
            -1,
            3
        ]
    }
}
```

---


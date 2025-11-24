# 📄 赛季（Season）配置说明  
（文件位于 profile\RELIFE\SEASONPASS\SEASONS）

你可以随意给这些 JSON 文件命名（使用拉丁字母）。  
关键是：**文件内部结构必须正确**。  
可以参考模组附带的示例。

该配置负责：

- 设置赛季内容  
- 定义每日 / 每周 / 赛季任务  
- 指定任务池  
- 指定等级奖励  
- 决定赛季启用时间  

系统会根据日期自动选择 **第一个符合时间范围的赛季**。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `seasonName` | `string` | 菜单中显示的赛季名称 |
| `seasonUniqueID` | `string` | 赛季唯一标识（用于存档和判定当前赛季） |
| `countDayTasks` | `int` | 玩家每天获得的每日任务数量 |
| `countWeekTasks` | `int` | 玩家每周获得的每周任务数量 |
| `countSeasonTasks` | `int` | 玩家整个赛季可获得的赛季任务数量 |
| `countDayTasksPremium` | `int` | 拥有 Premium 的玩家每天获得的每日任务数量 |
| `countWeekTasksPremium` | `int` | 拥有 Premium 的玩家每周获得的每周任务数量 |
| `countSeasonTasksPremium` | `int` | 拥有 Premium 的玩家赛季任务数量 |
| `dateStart` | `int array` | 赛季开始日期 `[日, 月, 年]` |
| `dateEnd` | `int array` | 赛季结束日期 `[日, 月, 年]` |
| `seasonDayTasksID` | `int array` | 每日任务池 ID 列表（必须多于 countDayTasks） |
| `seasonDayTasksPremiumID` | `int array` | Premium 玩家每日任务池 |
| `seasonWeekTasksID` | `int array` | 每周任务池（任务 ID 列表） |
| `seasonWeekTasksPremiumID` | `int array` | Premium 每周任务池 |
| `seasonSeasonTasksID` | `int array` | 赛季任务池 |
| `seasonSeasonTasksPremiumID` | `int array` | Premium 赛季任务池 |
| `seasonLevelsList` | `array` | 等级奖励配置列表 |

---

## 🧩 `seasonLevelsList` 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `levelNumber` | `int` | 等级编号 |
| `needPoints` | `string/int` | 解锁该等级需要的积分 |
| `allowShowInfoBeforeOpen` | `bool` | 是否允许在未解锁时看到奖励信息 |
| `hideRewardFree` | `bool` | 未解锁前隐藏免费奖励（显示问号图标） |
| `hideRewardPrem` | `bool` | 未解锁前隐藏 Premium 奖励 |
| `freeItemID` | `int` | 免费奖励 ID（来自 config_ItemsList.json）<br>若为负数（-1, -2...）则从随机奖励池中抽取 |
| `premiumItemID` | `int` | Premium 奖励 ID（同规则） |

📌 **随机奖励规则：**

- 写 `-1` = 使用随机奖励池中的第 1 个随机奖励组  
- 显示图标将变为 **战利品箱（Lootbox）图标**  
- 参见：  
  👉 https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_RandomItemsList.md

---

## 🎥 详细视频讲解（俄语）
https://youtu.be/nGtR_-UYTbQ

---

# 🧱 赛季完整结构示例

```json
{
    "seasonName": "April",
    "seasonUniqueID": "April_228",
    "countDayTasks": 4,
    "countWeekTasks": 3,
    "countDayTasksPremium": 1,
    "countWeekTasksPremium": 1,
    "dateStart": [1, 1, 2025],
    "dateEnd": [26, 8, 2025],
    "seasonDayTasksPremiumID": [800, 801],
    "seasonWeekTasksPremiumID": [802, 803],
    "seasonDayTasksID": [1, 2, 3, 4, 5, 6, 7],
    "seasonWeekTasksID": [8, 9, 10, 11, 12, 13, 14, 15],
    "seasonSeasonTasksID": [6],
    "seasonSeasonTasksPremiumID": [2, 3],
    "seasonLevelsList": [
        { "levelNumber": 1, "needPoints": 1000, "freeItemID": 1, "premiumItemID": 2 },
        { "levelNumber": 2, "needPoints": 1600, "freeItemID": -1, "premiumItemID": 3 },
        { "levelNumber": 3, "needPoints": 2800, "freeItemID": 4, "premiumItemID": 5 },
        { "levelNumber": 4, "needPoints": 3500, "freeItemID": -1, "premiumItemID": 6 },
        { "levelNumber": 5, "needPoints": 6200, "freeItemID": -1, "premiumItemID": 7 },
        { "levelNumber": 6, "needPoints": 7500, "freeItemID": 8, "premiumItemID": 9 },
        { "levelNumber": 7, "needPoints": 10000, "freeItemID": -1, "premiumItemID": 10 },
        { "levelNumber": 8, "needPoints": 11000, "freeItemID": -1, "premiumItemID": 11 },
        { "levelNumber": 9, "needPoints": 11250, "freeItemID": 1, "premiumItemID": 12 },
        { "levelNumber": 10, "needPoints": 13000, "freeItemID": 1, "premiumItemID": 2 }
    ]
}
```


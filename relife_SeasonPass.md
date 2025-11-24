# 📄 基础配置（config_MainSettings）说明

此配置用于存储 Season Pass（季票系统）的 **服务器全局设置**。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `currentSeasonID` | `string` | 当前服务器正在运行的赛季 ID。系统会根据此 ID 判断玩家是否属于当前赛季，不一致则重置玩家数据。 |
| `BuyPremiumBtnURL` | `string` | “购买高级通行证”按钮的跳转链接。如果留空，按钮不会显示。 |
| `urlButtonInMenuList` | `array` | 自定义菜单链接按钮列表。 |
| `EnableHTTPRequestPremiumCheck` | `bool` | 玩家加入服务器时，通过 HTTP GET 请求验证 Premium 状态。 |
| `HTTPRequestPremiumURL` | `string` | 用于 Premium 验证的接口地址，系统会附带玩家 GUID 发出 GET 请求。 |
| `adminSteamID` | `string array` | 拥有 Season Pass 管理员权限的 SteamID 列表。 |
| `premiumActivatedItem` | `string array` | 玩家只要持有这些物品即可在菜单中激活 Premium。物品在激活时会被删除。 |
| `changeDayPlayerAttempt` | `int` | 玩家每天可更换每日任务的次数。 |
| `changeWeekPlayerAttempt` | `int` | 玩家每周可更换每周任务的次数。 |
| `changeSeasonPlayerAttempt` | `int` | 玩家每赛季可更换季节任务的次数。 |
| `checkPremiumPriorityFile` | `bool` | 若玩家 SteamID 存在 priority.txt 文件中，则自动赋予 Premium（注意：**删除文件不会移除 Premium**）。 |
| `savePlayerDataBin` | `bool` | 启用后玩家数据将以二进制格式保存和加载。 |
| `savePlayerDataSQL` | `bool` | 启用后玩家数据将存入 KGB TOOL 数据库（需在 config 中添加 Virusoman_BP）。 |
| `enableMapMarkerForLocationTasks` | `bool` | 启用后，位置任务会在地图中显示标记（支持 LBMaster Advanced Groups、DayZ-Expansion-Navigation）。 |
| `showNotifyRewardSpawnDeny` | `bool` | 如果启用，当玩家尝试在不允许的位置领取奖励，系统会显示提示，而不是直接把奖励生成在脚下。 |
| `enableSpawnTransportInZone` | `bool` | 若启用，玩家领取载具奖励时只能在指定区域领取。 |
| `spawnTransportZone` | `vector` | 可领取载具的位置坐标。 |
| `spawnTransportZoneRadius` | `int` | 领取载具的区域半径。 |
| `dayTaskLastDate` | `int array` | 服务器每日任务的发布日期（天/月/年）。系统每日自动更新。 |
| `weekTaskLastDate` | `int array` | 服务器每周任务的发布日期（天/月/年）。系统每周自动更新。 |

---

## 🧩 urlButtonInMenuList 字段说明

> 可自定义多个菜单按钮，只要界面能放下即可。若不需要可删除。

| 字段 | 类型 | 说明 |
|------|------|------|
| `titleButton` | `string` | 鼠标悬停显示的文本 |
| `iconButton` | `string` | 按钮图标路径 |
| `openURL` | `string` | 点击后打开的链接 |

示例：

```json
{
    "titleButton": "YouTube",
    "iconButton": "relife_SeasonPass/images/youtube.edds",
    "openURL": "site.kz"
}
```

---

## 🧩 HTTPRequestPremiumURL 字段说明

> 系统将发送 GET 请求至该地址，附加玩家 GUID  
> 例如：  
> `https://yoursite.kz/getpremium.php?guid=GUID_PLAYER`

返回格式必须为：

```json
{
  "guid": "abc123",
  "premium": false
}
```

---

## 🎥 视频教程（俄语）
https://youtu.be/C14T219gq-M

---

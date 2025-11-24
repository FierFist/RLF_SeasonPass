# 📄 config_RandomItemsList 配置说明

该配置用于定义 **随机奖励池**。  
当玩家到达某个等级，并在 seasonLevelsList 中填写了负数奖励（例如 `-1`、`-2` 等），系统会从此配置中读取相应随机奖励池并生成随机奖励。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `randomItemsUniqueID` | `integer` | 随机奖励池的唯一 ID（不能重复）<br>在等级配置中使用负数引用：<br>例如等级里填 `-2` → 对应这里的 `2` |
| `randomItemsName` | `string` | 奖励名称（鼠标悬停显示） |
| `previewImage` | `string` | 奖励的预览图（建议使用 256×256）<br>可使用自带 1–10 号宝箱，例如：<br>`relife_SeasonPass/images/box_images/10.edds` |
| `rarityColor` | `string hexstring` | 根据物品“掉落概率区间”显示不同颜色。<br>格式：`"0.1-0.2": "0x78EB4B4B"`<br>**0.1–0.2** = 几率区间（含边界）<br>**0x78EB4B4B** = HEX 颜色（0x78 为透明度） |
| `itemsIDList` | `integer:float` | 物品 ID → 掉落权重（0–1）。<br>权重越高，概率越大。物品 ID 来自：[config_ItemsList](https://github.com/virusomanvs/relife_SeasonPass/blob/main/config_ItemsList.md) |

---

![image](https://github.com/user-attachments/assets/89e0c7ca-eebc-436f-a658-f4a5f01742cf)

---

## 🎥 视频讲解（俄语）
https://youtu.be/zqg-qNEU1EY

---

## 🧱 配置示例

```json
{
    "randomItemsUniqueID": 1,
    "randomItemsName": "随机物品 [木箱]",
    "previewImage": "relife_SeasonPass/images/box_images/2.edds",
    "rarityColor": {
        "0.1-0.2": "0x78EB4B4B",
        "0.3-0.4": "0x78D32CE6",
        "0.5-0.6": "0x788847FF",
        "0.7-0.8": "0x784B69FF",
        "0.9-1.0": "0x785E98D9"
    },
    "itemsIDList": {
        "1": 0.1,
        "2": 0.2,
        "3": 0.3,
        "4": 0.4
    }
},
{
    "randomItemsUniqueID": 3,
    "randomItemsName": "随机物品 [金箱]",
    "previewImage": "relife_SeasonPass/images/box_images/10.edds",
    "itemsIDList": {
        "1": 0.1,
        "2": 0.2,
        "3": 0.3,
        "4": 0.4
    }
}
```

---

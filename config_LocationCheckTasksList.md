# 📄 config_LocationCheckTasksList 配置说明

该配置用于为 **LocationCheck（位置检查）** 类型任务添加额外参数。

此类任务用于：  
⭐ 玩家前往指定地点后任务计数  
⭐ 可设置多个地点  
⭐ 可结合 taskParamNumber 控制需要访问的地点数量  

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹） |
| `locationLists` | `vector array` | 需要访问的世界坐标列表（可填 1 个或多个）<br>如有多个地点，需要在任务主配置中设置 taskParamNumber 为地点数量 |
| `locationRadiuses` | `int array` | 每个地点对应的半径范围（数组长度必须与 locationLists 完全一致） |

---

## 📌 参数要求说明

- 如果有 5 个坐标 → `locationRadiuses` **必须有 5 个值**  
- 半径用于判断玩家是否进入该区域  
- 坐标格式为：  
  ```
  [X, Y, Z]
  ```

---

## 🧱 配置示例

```json
{
    "taskID": 222,
    "locationLists":  [
        [13910.5, 5.169, 11821.8],
        [6129.59, 3.4455, 7272.06]
    ],
    "locationRadiuses":  [
        100,
        100
    ]
}
```

---


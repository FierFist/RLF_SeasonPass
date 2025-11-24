# 📄 config_WalkDistanceList 配置说明

该配置用于为 **WalkDistance（步行距离任务）** 类型添加额外参数。

此类任务让玩家 **步行达到指定距离** 后完成任务。  
距离要求在主任务配置中通过 `taskParamNumber` 设置（单位：米）。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹） |

---

## 📌 说明

- 此配置文件只用来声明任务属于 WalkDistance 类型  
- 具体距离需求写在主任务中的 `taskParamNumber`  
  例如：  
  ```json
  "taskParamNumber": [5000.0]   // 玩家需要走 5000 米
  ```

---

## 🧱 配置示例

```json
{
    "taskID": 9001
}
```

---


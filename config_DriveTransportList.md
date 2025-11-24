# 📄 config_DriveTransportList 配置说明

该配置用于为 **DriveTransport** 类型的任务设置额外参数。

此类任务要求玩家在**驾驶车辆**时累积行驶距离，达到要求后即可完成任务。

---

## 🧩 参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskID` | `integer` | 此配置对应的任务 ID（来自 TASKS 文件夹中的任务列表） |
| `transportType` | `string array` | 允许计数的车辆类名列表（不支持继承，必须精确匹配类名） |

---


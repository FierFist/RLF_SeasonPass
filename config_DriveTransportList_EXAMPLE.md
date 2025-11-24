# 📄 在车辆中行驶任务的添加示例

下面展示如何添加一个 **驾驶汽车并行驶指定距离** 的任务。  
各参数的详细说明请参考对应的配置文件：**config_DriveTransportList.json**

---

## 🧩 当 **typeTask = DriveTransport** 时的附加参数说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `taskParamNumber` | `float array` | 需要行驶的距离（单位：米）。用于任务描述与 UI 正确显示。 |

---

## ✔️ 1. 在 TASKS 文件夹中添加主任务配置  
（任务主配置结构说明请见：  
[config_TasksList.json](https://github.com/virusomanvs/relife_SeasonPass/blob/main/TASKS.md)）

示例：

```json
{
    "taskID": 1502,
    "givePoints": 1000,
    "typeTask": "DriveTransport",
    "iconTask": "relife_SeasonPass/images/task_icons/volga.edds",
    "titleTask": "范·迪塞尔",
    "descTask": "驾驶 Volga 行驶 10000 米。",
    "taskParamNumber": [
        10000.0
    ],
    "taskParamText": []
}
```

---

## ✔️ 2. 在 config_DriveTransportList.json 中指定车辆类型  
taskID 必须与主任务配置一致，以正确关联配置。

示例：

```json
{
    "taskID": 1502,
    "transportType": [
        "CivilianSedan"
    ]
}
```

---

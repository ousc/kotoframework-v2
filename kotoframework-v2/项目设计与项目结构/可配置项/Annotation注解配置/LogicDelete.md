---
sticker: emoji//1f4cc
---
#class #注解 

> [!NOTE] 简介 
> 用于设置该表`是否启用逻辑删除`和设置`逻辑删除列`和`删除时间列`，该注解设置的优先级高于[[setLogicDelete]]
##### 成员变量

| 变量名                | 类型         | 默认值    | 解释       |
| ------------------ | ---------- | ------ | -------- |
| `enabled`          | `Boolean?` | `true` | 是否开启逻辑删除 |
| `column`           | `String?`  | 遵循全局设置 | 逻辑删除列    |
| `deleteTimeColumn` | `String?`  | 遵循全局设置 | 逻辑删除时间列  |
| `markAsDelete`     | `String?`  | `"1"`  | 标识为删除的值  |
| `markNotDelete`    | `String?`  | `"0"`  | 标识为未删除的值 |

使用示例：

```kotlin
@Table(name = "tb_user") 
@LogicDelete(enabled = true, column = "deleted", deleteTimeColumn = "delete_time")
data class User(): KPojo
```

> 该注解仅能在Class级别使用
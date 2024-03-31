---
sticker: emoji//1f4cc
---
#class #注解 

> [!NOTE] 简介 
> 用于指定该表`每行的创建时间`字段名称，优先级高于[[setCreateTime]]

##### 成员变量

| 变量名       | 类型         | 默认值    | 解释   |
| --------- | ---------- | ------ | ---- |
| `enabled` | `Boolean?` | true   | 是否开启 |
| `column`  | `String?`  | 遵循全局设置 | 列名   |

使用示例：

```kotlin
@CreateTime(column = "create_time") data class User(): KPojo
```

> 该注解仅能在Class级别使用
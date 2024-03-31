---
aliases:
  - Column
sticker: emoji//1f4cc
---
#class #注解 

> [!NOTE] 简介
> 用于指定该属性绑定的数据库列名，优先级高于根据属性获取列名的通用设置([[setFieldNamingStrategy]])

##### 成员变量

| 变量名           | 类型                            | 默认值    | 解释                                                 |
| ------------- | ----------------------------- | ------ | -------------------------------------------------- |
| `name`        | `String?`                     | `null` | 列名                                                 |
| `jsonField`   | `Boolean?`                    | `null` | 是否为解析JSON列                                         |
| #jsonResolver | KClass<[[KotoJsonResolver]]>? | `null` | 用于为某json列提供单独的处理逻辑，优先级高于[[setDefaultJsonResolver]] |

使用示例：
```kotlin
data class User(
	@Column(name = "username") val userName: String? = null,
	@Column(jsonField = true) val strList: List<String>? = null,
	@Column(jsonField = true, jsonResolver = CustomJsonResolver::class) val userList: List<User>? = null
): KPojo
```

>该注解仅能在Property级别使用
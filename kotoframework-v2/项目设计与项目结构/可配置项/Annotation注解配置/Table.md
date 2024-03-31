---
sticker: emoji//1f4cc
---
#class #注解

> [!NOTE] 简介
> 用于指定该KPojo类绑定的数据库表名，优先级高于根据类名获取表名的通用设置([[setTableNamingStrategy]])

##### 成员变量

|变量名|类型|解释|
|---|---|---|
|`name`|`String`|列名|

使用示例：

```kotlin
@Table(name = "tb_user") data class User(): KPojo
```

> 该注解仅能在Class级别使用
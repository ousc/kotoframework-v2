---
sticker: emoji//1f4cc
---
#class #注解

> [!NOTE] 简介
> 用于指定该KPojo类绑定的数据库表名，优先级高于根据类名获取表名的通用设置([[setTableNamingStrategy]])

##### 成员变量
<span style='color:var(--mk-color-purple)'>val</span> <span style='color:var(--mk-color-teal)'>name</span>: <span style='color:var(--mk-color-red)'>String</span>

使用示例：
```kotlin
@Table(name = "user") data class User: KPojo
```

>该注解仅能在`Class`级别使用
---
sticker: emoji//1f4d5
---
#class 

> [!NOTE] 简介：
> 命名策略，用于设置数据库表名（或列名）与KPojo对象名（或属性名）之间的映射关系。可以使用驼峰命名、下划线命名或其他命名策略，以便实现对象与数据库表的映射。

##### 成员函数
```kotlin file:1.数据库表名(列名)转换为KPojo对象名(属性名)
fun db2k(name: String): String
```

```kotlin file:1.KPojo对象名(属性名)转换为数据库表名(列名)
fun k2db(name: String): String
```


> Koto默认提供line2hump和 hump2line 表名转换函数用于将数据库表名（列名）和KPojo对象名（属性名）从驼峰命名、下划线命名之间相互转换。
> 你可以使用Koto函数或自己编写转换函数来实现表名与对象名的灵活映射。
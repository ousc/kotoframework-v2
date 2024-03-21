---
sticker: emoji//1f4cc
---
#class #注解

> [!NOTE] 简介
> 用于指定该KPojo类绑定的数据库表名，优先级高于根据类名获取表名的通用设置


| 列           | 值                                              |
| ----------- | ---------------------------------------------- |
| description | 表名注解，当没有注解时，表名默认为类名调用namingStrategy转换后的名称      |
| for         | Class                                          |
| example     | `@Table(name = "user") data class User: KPojo` |

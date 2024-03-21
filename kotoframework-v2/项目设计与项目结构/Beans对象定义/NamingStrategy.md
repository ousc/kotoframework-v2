---
sticker: emoji//1f4d5
---
#class 

> [!NOTE] 简介：
> 命名策略，用于设置数据库表名（或列名）与KPojo对象名（或属性名）之间的映射关系。可以使用驼峰命名、下划线命名或其他命名策略，以便实现对象与数据库表的映射。

##### 表名转换为KPojo对象名函数：
<span style="color:#c73ef9">val</span> <span style="color:#0ca9ac">tableName2KPojoName</span>: (<span style="color:#c00000">String</span>) -> <span style="color:#c00000">String</span>

##### KPojo对象名转换为 数据库表名函数：
<span style="color:#c73ef9">val</span> <span style="color:#0ca9ac">kPojoName2TableName</span>: (<span style="color:#c00000">String</span>) -> <span style="color:#c00000">String</span>)

> Koto默认提供line2hump和 hump2line 表名转换函数用于将数据库表名转换为KPojo对象名从驼峰命名、下划线命名之间相互转换。你可以使用这些函数或自己编写转换函数来实现表名与对象名的灵活映射。
---
sticker: emoji//1f4cc
---
#class #注解 

> [!NOTE] 简介 
> 用于指定<span style='color:var(--mk-color-red)'>Date</span>或<span style='color:var(--mk-color-red)'>DateTime</span>类型数据转为String时进行格式化时的格式

##### 成员变量

| 变量名      | 类型       | 解释  |
| -------- | -------- | --- |
| `format` | `String` | 列名  |

使用示例：

```kotlin
@Table(name = "tb_user") data class User(
	val originalDate: Date? = null,
	@DateTimeFormat("%Y-%m-%d") val date: String? = null,
	@DateTimeFormat("%Y-%m-%d %H:%i:%s") val dateTime: String = null
): KPojo
```

> 该注解仅能在Property级别使用
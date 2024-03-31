---
sticker: emoji//1f4cc
---
#class #注解 

> [!NOTE] 简介
> 用于设置该列通过Koto创建行时的默认值

##### 成员变量

| 变量名     | 类型       | 解释  |
| ------- | -------- | --- |
| `value` | `String` | 默认值 |
使用示例：
```kotlin
data class User(
	@Default(value = "1") val flag: Int? = null
): KPojo
```

>该注解仅能在Property级别使用
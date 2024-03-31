---
sticker: emoji//1f50c
---
#interface 


> [!NOTE] 简介
> 使用Koto的JSON解析和转换能力时，配置类需继承此接口，我们不限制您使用第三方库如Gson、Jackson、fastjson等实现JSON字符串和各种数据结构之间的转换。

##### 成员函数:
```kotlin file:1.将字符串解析为指定类型T
fun <T> parseJSON(json: String, kClass: KClass<*>): T
```

```kotlin file:2.将变量转换为JSON字符串
fun toJSONString(obj: Any): String
```

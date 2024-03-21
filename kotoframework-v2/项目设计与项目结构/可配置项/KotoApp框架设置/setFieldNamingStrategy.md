---
sticker: emoji//1f527
---
#function 

> [!NOTE] 简介
> 设置数据库列名与KPojo的Property的默认转换规则，优先级低于注解([[Column]])配置

接受参数：
- [[NamingStrategy]]

返回值：
- [[KotoApp]]

使用示例：
```kotlin
KotoApp.setFieldNamingStrategy(NamingStrategy(line2hump, hump2line))
```

---
sticker: emoji//1f527
---
#function 

> [!NOTE] 简介
> 设置数据库表名与KPojo的默认转换规则，优先级低于注解([[Table]])配置

接受参数：
- [[TableNamingStrategy]]

返回值：
- [[KotoApp]]

使用示例：
```kotlin
KotoApp.setTableNamingStrategy(TableNamingStrategy(line2hump, hump2line))
```

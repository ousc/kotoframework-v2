---
sticker: emoji//1f527
---
#function 

> [!NOTE] 简介
> 设置默认的Json处理器，优先级低于注解([[Column]])的 #jsonResolver 设置

接受参数：
- [[KotoJsonResolver]]

返回值：
- [[KotoApp]]

使用示例：
```kotlin
class CustomJsonResolver(): KotoJsonResolver{ ... }
KotoApp.setDefaultJsonResolver(CustomJsonResolver())
```

---
sticker: emoji//1f527
---
#function 

> [!NOTE] 简介
> 用于设置动态的数据源，生效的优先级别高于[[setDataSource]]

接受参数：
- () -> [[KotoJdbcWrapper]]

返回值：
- [[KotoApp]]

使用示例：
```kotlin
KotoApp.setDynamicDataSource {
	if(someCondition){
		SpecificJdbcWrapper
	} else {
		AnotherJdbcWrapper
	}
}
```

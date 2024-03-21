---
sticker: emoji//1f418
---
#kotlin-class #abstract 
```kotlin file:通过传入的sql和Map查询数据列表
abstract fun forList(sql: String, paramMap: Map<String, Any?> = mapOf()): List<Map<String, Any>>  
```

```kotlin file:通过传入的sql和Map查询行数据
abstract fun forMap(sql: String, paramMap: Map<String, Any?> = mapOf()): Map<String, Any>?  
```

```kotlin file:通过传入的sql和Map查询单行数据(支持类型解析)
abstract fun <T> forObject(sql: String, paramMap: Map<String, Any?> = mapOf(), clazz: Class<T>): T?  
```

```kotlin file:根据传入的sql和Map更新数据行
abstract fun update(sql: String, paramMap: Map<String, Any?> = mapOf()): Int
```

  ```kotlin file:根据传入的sql和Map批量执行更新数据行
abstract fun batchUpdate(sql: String, paramMaps: Array<Map<String, Any?>> = arrayOf()): IntArray 
```

Connection的URL
<span style="color:#c73ef9">abstract</span> <span style="color:#c73ef9">val</span> <span style="color:#0ca9ac">url</span>: <span style="color:#0ca9ac">String</span>
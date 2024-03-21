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


abstract fun update(sql: String, paramMap: Map<String, Any?> = mapOf()): Int  
abstract fun batchUpdate(sql: String, paramMaps: Array<Map<String, Any?>> = arrayOf()): IntArray  
  
inline fun <reified T : KPojo> update(kPojo: T, vararg fields: Field): UpdateAction<T> {  
    return com.kotoframework.function.update.update(kPojo, *fields, jdbcWrapper = this)  
}  
  
inline fun <reified T : KPojo> remove(KPojo: T): RemoveAction<T> {  
    return com.kotoframework.function.remove.remove(KPojo, jdbcWrapper = this)  
}  
  
inline fun <reified T : KPojo> create(kPojo: T): CreateWhere<T> {  
    return com.kotoframework.function.create.create(kPojo, jdbcWrapper = this)  
}  
  
abstract val url: String
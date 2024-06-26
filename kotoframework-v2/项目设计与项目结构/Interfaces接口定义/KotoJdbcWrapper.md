---
sticker: emoji//1f50c
---
#interface

> [!NOTE] 简介
> 数据源的包装类，用于为Koto提供数据库访问能力

##### 成员变量：

| 变量名      | 类型         | 解释             |
| -------- | ---------- | -------------- |
| `url`    | `String`   | Connection URL |
| `dbType` | [[DBType]] | 数据源类型          |

##### 成员函数：
```kotlin file:1.通过传入的sql和Map查询数据列表
fun forList(sql: String, paramMap: Map<String, Any?> = mapOf()): List<Map<String, Any>>  

fun forList(
	sql: String,
	paramMap: Map<String, Any?>,
	kClass: KClass<*>
): List<Any>
```

```kotlin file:2.通过传入的sql和Map查询行数据
fun forMap(sql: String, paramMap: Map<String, Any?> = mapOf()): Map<String, Any>?  
```

```kotlin file:3.通过传入的sql和Map查询单行数据(支持类型解析)
fun <T> forObject(sql: String, paramMap: Map<String, Any?> = mapOf(), clazz: Class<T>): T?  

fun forObject(
	sql: String,
	paramMap: Map<String, Any?>,
	withoutErrorPrintln: Boolean = false,
	kClass: KClass<*>
): Any

fun forObjectOrNull(
	sql: String,
	paramMap: Map<String, Any?>,
	kClass: KClass<*>
): Any?
```

```kotlin file:4.根据传入的sql和Map更新数据行
fun update(sql: String, paramMap: Map<String, Any?> = mapOf()): Int
```

  ```kotlin file:5.根据传入的sql和Map批量执行更新数据行
fun batchUpdate(sql: String, paramMaps: Array<Map<String, Any?>> = arrayOf()): IntArray 
  ```


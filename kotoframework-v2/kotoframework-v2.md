---
_filters: []
_contexts: []
_links: []
_sort:
  field: rank
  asc: false
  group: false
sticker: emoji//1f525
---
##### Koto是一款前所未有的、开创性的、现代化的kotlin ORM框架。

##### 它基于K2编译器插件分析表达式树，实现了简洁而又语义化的数据持久层框架，让使用者在开发过程中可以更加高效地操作数据。

##### Koto的设计初衷是为了弥补现有ORM框架中不足之处，并针对kotlin后端开发、移动端开发以及KMM多平台开发做了特别的优化。不仅如此，它还支持多种常见关系型数据库，包括Mysql、Oracle、Postgres、Mssql、SQLite、DB2、Sybase和H2，以及国产数据库OceanBase和DM8。

##### 通过编写kotlin k2编译器插件，Koto 2.0实现了更加强大和语义化的ORM功能。它是一个轻量级的框架，为开发者提供了一种高效的数据持久化解决方案。

-------
>示例：
```kotlin file:查询示例
// 1. 条件查询 / 查询单个字段 / 使用query()查询List<Map>结果
val users: List<Map<String, Any>> = User(1).select{ where() }.query()

// 2.多条件查询 / 查询多个字段 / 带分页 / 带去重 / 带排序
val (users, total): Pair<List<User>, Int> = 
		User().select { it.id + it.userName + it.authCode }
			.where { it.id == 1 }
			.by{ it.id }
			.page(1, 10)
			.orderBy{ it.updateTime.desc }
			.distinct()
			.withTotal()
			.queryForList()


// 3.连表查询
val result: List<Map<String, Any>> = 
		User().join(ShoppingCart(), Good()){ user, cart, good ->
			leftJoin(cart)
				.on(user.id == cart.id && user.age > 35)
			rightJoin(good)
				.on(good.id == cart.id)
			select(user, good.id, cart.id)
			where (
				user.id == 1 &&
				user.age >= 20 &&
				user.email like "%@qq.com" &&
				user.telephone notLike "159%" &&
				(
					user.userName in listOf("a", "b") || 
					user.id !in listOf(1, 2, 3)
				) &&
				user.nickname.notNull &&
				user.age between 1..2 &&
				user.age notBetween 1..2
			)
			groupBy(user.age)
			page(1, 100)
		}
		.withTotal()
		.query()

```

------
```kotlin file:插入示例
// 1.插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		User(1).insert().execute()

// 2.根据主键更新或插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		User(1).upsert()
			.set{ it.createTime = "YYYY-MM-DD" }
			.execute()
			
// 3.根据部分列更新或插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		User(1).upsert{ it.id }
			.onDuplicate() // 默认
			.execute()

// 4.根据部分列更新或插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		User(1).upsert{ it.id }
			.by{ it.name + it.email }
			.execute()
```

------
```kotlin file:更新示例
// 更新行
val affectRowNumber: Int = 
		User(1).update()
			.set { it.id = 2 }
			.by { it.id }
			.execute()
				
// 更新行
val affectRowNumber: Int = 
		User(2).update{ it.id }
			.where{ it.id == 1 }
			.execute()
```

------
```kotlin file:删除示例
// 删除行
val affectRowNumber: Int = 
		User.remove()
			.by { it.id + it.status }
			.execute()
				
val affectRowNumber: Int = 
		User.remove()
			.where { it.id > 1 && it.id < 10  }
			.execute()
```

------

> [!NOTE] 此章节包含以下内容
> [[README]]
> [[Roadmap]]
> [[快速上手|快速上手]]
>  [[项目设计与项目结构]]


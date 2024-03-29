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
## Koto 是一个数据持久层框架，设计用于 Kotlin，轻量级，现代化。

Koto 2.0旨在通过编写kotlin k2编译器插件，实现更加强大且语义化的orm功能。

-------
>示例：
```kotlin file:查询示例
// 1. 条件查询 / 查询单个字段 / 使用query()查询List<Map>结果
val users: List<Map<String, Any>> = User(1).select{ where() }.query()

// 2.多条件查询 / 查询多个字段 / 带分页 / 带去重 / 带排序
val (users, total): Pair<List<User>, Int> = 
		User().select { 
			col(it::id, it::userName, it::authCode)
			where (it::id == 1)
			// filter (it::id == 1)
			by(it::id)
			page(1, 10)
			sortBy(it.updateTime.desc)
			distinct()
		}
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
			groupBy (user.age)
			page(1, 100)
		}
		.withTotal()
		.query()

```

------
```kotlin file:插入示例
// 1.插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		insert(User(1)).execute()

// 2.根据主键更新或插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		upsert(User(1))
			.set { it.createTime to "YYYY-MM-DD" }
			.execute()

// 3.根据部分列更新或插入一行数据
val affectRowNumber: Pair<Int, Int> = 
		upsert(User(1))
			.on { it.name + it.email}
			.execute()
```

------
```kotlin file:更新示例
// 更新行
val affectRowNumber: Int = 
		update(User(1))
			.set { it.id to 2 }
			.by { it.id }
			.execute()
				
// 更新行
val affectRowNumber: Int = 
		update(User(2))
			.set { it.id }
			.where{ it.id == 1}
			.execute()
```

------
```kotlin file:删除示例
// 删除行
val affectRowNumber: Int = 
		delete(User(1))
			.by { it.id }
			.execute()
				
val affectRowNumber: Int = 
		delete(User(1))
			.where { it.id.eq  }
			.execute()
```

------

> [!NOTE] 此章节包含以下内容
> [[README]]
> [[Roadmap]]
> [[快速上手|快速上手]]
>  [[项目设计与项目结构]]


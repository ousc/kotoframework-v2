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

>示例：
```kotlin file:Example.kt
//查询示例
// 1. 条件查询 / 查询单个字段 / 使用query()查询List<Map>结果
val users: List<Map<String, Any>> = from<User>()
                .selectAll().where { it.id == 1 }.query()

// 1.多条件查询 / 查询多个字段 / 带分页 / 带去重 / 带排序
val (users, total): List<User> = from<User>()
                .select { it.userName + it.authCode + it.id }
                .where { it.id == 1 }
                .page(1, 10)
                .orderBy { it.updateTime.desc() }
                .distinct()
                .withTotal()
	            .queryForList()


//连表查询
val result = from<User>()
                .leftJoin<ShoppingCart>{ user, cart ->
	                user.id == cart.id && user.age > 35
                }
                .rightJoin<Good>(Good(1)){ user, cart, good ->
	                good.id == cart.id
                }
                .select { user, cart, good ->
	                user + cart.id + good.id
                }
                .where { user, cart, good ->
                    user.id == 1 &&
					user.age >= 20 &&
					user.email like "%@qq.com" &&
					user.telephone notLike "159%" &&
					(
						user.userName in listOf("a", "b", "c") || 
						user.id !in listOf(1, 2, 3)
					) &&
					user.nickname.notNull &&
					user.age between 1..2 &&
					user.age notBetween 1..2
                }
                .groupBy { user, _, _ -> user.age }
                .page(1, 100)
                .withTotal()
                .query()

// 插入一行数据
val (affectRowNumber, lastInsertId) = insert(User(1)).execute()

// 根据主键更新或插入一行数据
val (affectRowNumber, lastInsertId) = upsert(User(1)).execute()

// 根据部分列更新或插入一行数据
val (affectRowNumber, lastInsertId) = upsert(User(1))
				 .on{ it.name + it.email}
				 .execute()
// 更新行
val affectRowNumber = update(User(1)).set{}

```

## 此章节包含以下内容：

> [!NOTE] RoadMap
> [[Roadmap]]

> [!NOTE] 项目结构
> [[项目结构]]

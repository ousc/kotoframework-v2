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
```kotlin nums {3-4,7-15}
//查询示例
// 1. 条件查询 / 查询单个字段 / 使用query()查询List<Map>结果
val users: List<Map<String, Any>> = from<User>()
				.select { it::userName }.where { it::id == 1 }.query()

// 1.多条件查询 / 查询多个字段 / 带分页 / 带去重 / 带排序
val (users, total): List<User> = from<User>()
                .select { it::userName + it::authCode + it::id }
                .where { it.id == 1 &&  }
                .page(1, 10)
                .orderBy { it::updateTime.desc() }
                .distinct()
                .withTotal {
	                queryForList()
                }


//连表查询

```

## 此章节包含以下内容：

> [!NOTE] RoadMap
> [[Roadmap]]

> [!NOTE] 项目结构
> [[项目结构]]

#interface 

```
    fun forList(
        jdbc: KotoJdbcWrapper? = null,
        sql: String,
        paramMap: Map<String, Any?>,
        kClass: KClass<*>
    ): List<Any>

    fun forObject(
        jdbc: KotoJdbcWrapper? = null,
        sql: String,
        paramMap: Map<String, Any?>,
        withoutErrorPrintln: Boolean = false,
        kClass: KClass<*>
    ): Any

    fun forObjectOrNull(
        jdbc: KotoJdbcWrapper? = null,
        sql: String,
        paramMap: Map<String, Any?>,
        kClass: KClass<*>
    ): Any?
```
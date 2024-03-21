---
sticker: emoji//1f50c
---
interface KJSONParser {  
    fun parseJSON(json: String): Any  
    fun toJSONString(obj: Any): String  
}